---
description: Или roles-service
icon: circle-r
---

# Сервис ролей

roles-service – сервис, который управляет всеми ролями. Только он может постучаться в [LuckPerms](https://luckperms.net/) и выдать, снять и получить роли. Централизированная логика позволяет нам минимизировать непредсказуемую выдачу ролей и отказаться от самых разных запросов в LP из каждого сервиса, бота и плагина.&#x20;

Внутри сервиса описаны методы для отправки запросов в LP API и обработку ответов. Технически, это `gRPC/NATS->HTTP->gRPC/NATS`тунель.&#x20;

## NATS подписчик

Сервер слушает вайлдкард в меседж брокере, получает запросы на выдачу и снятие ролей. Запросы описаны в Protobuf и выглядят примерно так:

```protobuf
enum EditGroupsAction {
  UNDEFINED = 0;
  ADD = 1;
  REMOVE = 2;
}

enum RequestedFrom {
  ANY = 0;
  DISCORD = 1;
}

message EditGroupsRequest {
  EditGroupsAction type = 1;
  uint64 id = 2;
  repeated string names = 3;
  RequestedFrom requested_from = 4;
}

message EditGroupsResponse {
  repeated string names = 3;
}
```

`EditGroupsAction.Add`добавляет роли, `EditGroupsAction.REMOVE` – снимает. Если сервису пришел `UNDEFINED` , запрос был поврежден, и ничего не произойдет. \
`RequestedFrom`используется для логирования.

## gRPC сервер

Сервис выдает списки ролей, прав и весов ролей игроков по gRPC. Запросы и ответы выглядят так:

```protobuf
rpc GetGroups(GetByIdRequest) returns (GetGroupsResponse);
rpc GetNodes(GetByIdRequest) returns (GetNodesResponse);
rpc GetWeights(GetWeightsRequest) returns (GetWeightsResponse);  
```

```protobuf
message GetByIdRequest {
  uint64 id = 1;
}

message GetGroupsResponse {
  uint64 id = 1;
  repeated string groups = 2;
}

message Node {
  string key = 1;
  string type = 2;
  bool value = 3;
}

message GetNodesResponse {
  uint64 id = 1;
  repeated Node nodes = 2;
}

message GetWeightsRequest {
  uint64 id1 = 1;
  uint64 id2 = 2;
}

message GetWeightsResponse {
  int32 weight1 = 1;
  int32 weight2 = 2;
}
```

Для получения прав сервис сходит в LP, получит список нод ([Node](https://luckperms.net/wiki/Developer-API-Usage#the-basics-of-node)), спарсит в формат сообщения и отправит клиенту. Если же запрошен список груп, произойдет то же самое, за исключением, что сервис отдаст только те ноды, которые имеют префикс `group.`

## Интеграция с [teams-service](servis-obshin.md)

Сервис умеет автоматически добавлять и удалять игроков-членов государственных структур в соответствующие общины. Для этого в него нужно добавить интеграцию:

```protobuf
rpc AddTeamIntegration(AddTeamIntegrationRequest) returns (google.protobuf.Empty);
```

```protobuf
message AddTeamIntegrationRequest {
    string roleName = 1;
    int64 teamId = 2;
}
```

Сервис сохранит это в свою базу данных. После чего, если выданная роль имеет интеграцию, сервис асинхронно пойдет добавлять игроков в общины. При снятии ролей произойдет обратное.&#x20;

_Может быть добавлено несколько интеграций для одной роли._&#x20;

Интеграции можно удалять и получать:

```protobuf
rpc RemoveTeamIntegration(RemoveTeamIntegrationRequest) returns (google.protobuf.Empty);
rpc GetTeamIntegrations(google.protobuf.Empty) returns (GetTeamIntegrationsResponse);
```

```protobuf
message RemoveTeamIntegrationRequest {
    string roleName = 1;
    int64 teamId = 2;
}

message Integration {
    int64 id = 1;
    string roleName = 2;
    int64 teamId = 3;
}

message GetTeamIntegrationsResponse {
  repeated Integration Integrations = 1;
}
```







