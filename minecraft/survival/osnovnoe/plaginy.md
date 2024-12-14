# Плагины

## Основные

*   [**CoreProtect**](https://github.com/PlayPro/CoreProtect)

    логирует ивенты в мире, позволяет находить и откатывать действия игроков
*   [**AuxProtect** ](https://github.com/ks-hl/AuxProtect)

    Похож на корпротект, но логирует намного больше ивентов и предоставляет крутой функционал отката инвентарей
*   [**emotecraft**](https://modrinth.com/plugin/emotecraft-bukkit)

    серверный клиент эмоуткрафта
*   [**GSit**](https://github.com/gecolay/GSit)

    добавляет всеми любимый /sit, /crawl и /lay
*   [**Hat**](https://www.spigotmc.org/resources/hat.33980/)

    позволяет надевать предметы на голову через команду и инвентарь
*   [**PlasmoVoice**](https://plasmovoice.com/)

    голосовой чат от апехума 😊
*   [**SkinsRestorer**](https://github.com/SkinsRestorer/SkinsRestorer/)

    скины, добавляет /skin, мы используем его в плагине на рп роли, через него работают скины и аватарки в нашем бекенде
*   [**squaremap**](https://github.com/jpenilla/squaremap)

    обеспечивает работу карты мира на сайте, потом все миры объединяются в одну с помощью [LiveAtlas](https://github.com/JLyne/LiveAtlas)(мы используем собственный сбилженный докер образ c [static-web-server](https://ghcr.io/static-web-server/static-web-server:latest))
*   [**geyser** ](https://modrinth.com/plugin/geyser/version/u2OqHDfS)(Velocity)

    шакальный плагин на то чтобы можно было пускать игроков с бедрока на наш джава сервер, его всем лень настраивать, поэтому если вы хотите зайти с бедрока, то лучше открыть тикет
*   [**maintenance**](https://modrinth.com/plugin/maintenance/version/sAW3iflU) (Velocity)

    позволяет закрыть сервер для обычных игроков и в мотд написать "тех. работы"
*   [**velocitab** ](https://github.com/WiIIiam278/Velocitab)(Velocity)

    межсерверный плагин на таб
*   #### Аддоны для Plasmo Voice

    * **pv-addon-broadcast** - общесерверное вещание
    * **pv-addon-discs** — диски
    * **pv-addon-groups** — группы
    * **pv-addon-lavaplayer-lib -** либа для работы дисков
    * **pv-addon-priority** — приоритетный войс
    * **pv-addon-sculk** — позволяет скалк сенсорам и варденам слышать игроков
    * **pv-addon-spectator** — утилиты для спектаторов
    * **pv-addon-whisper** — добавляет шепот (тихий локальный чат)

    [**CoreProtectTNT**](https://github.com/Ghost-chu/CoreProtectTNT)

    дополнение к CoreProtect, позволяет связывать взрывы с его инициатором: кто заагрил крипера и кто поджег динамит. проект архивирован

## Наши плагины

*   **MurChat**

    мощный плагин на чат
*   **GlobalRespawn**

    делает респавны в нашей системе мультимиров ванильной&#x20;
*   **TheEndTeleport**

    ловит пакет входа в портал в энд и подменяет нашим форвардингом по прокси. Работает с апи глобал респавна
*   **SkipAdvancementSend**

    При переходе между мирами игрок может переполучать ачивки, этот плагин фиксит это тем, что обрубает пакеты о новых ачивках в первые секунды на новом сервере&#x20;
*   **LinkedPortals**

    Порталы между мирами
*   **Punishments**

    Клиент punishments-service. Добавляет /warn, /warns, /fwarn, /rwarn, /mute, /unmute, /ban, /unban, /eblan
* **RpRoles**\
  клиент rproles-service. Добавляет систему РП персонажей в игру - /ch
*   **Spit**

    добавляет плевки - /spit
*   **murcord** (Velocity)

    помогает мурчату работать на все сервера, обрабатывает входы и выходы игроков
*   **auth** (Velocity)

    плагин на авторизацию, работает как вайтлист по наличию проходки и банам, авторизует юзеров по айпи, лицензии и паролю. сохраняет сессии для сервиса статистик, отправляет в лимбо для авторизации по ссылке

{% hint style="info" %}
Автор всех наших плагинов - [Apehum](https://github.com/Apehum). Кроме spit, его написал стажер из eDD (digital drugs education program)
{% endhint %}

## Утилиты

* [**LuckPerms**](https://luckperms.net/)\
  Плагин на пермишены, через него работают проходки, роли префиксы и цвета ников. Синхронизирован с надим дискордом
*   [**HuskSync** ](https://github.com/WiIIiam278/HuskSync)

    Синхронизирует данные игрока (инвентарь, опыт и прочее) между мирами. Платный, но можно сбилдить самому
*   [**BetterChatBubbles**](https://www.spigotmc.org/resources/better-chat-bubbles%EF%B8%8F%EF%B8%8F%EF%B8%8F-%E2%AD%90-1-19-4-1-21-%E2%9C%85-packet-based-%E2%9C%85-animated-%E2%9C%85-api.115811/)

    Плагин на чатбабблы над головой. Есть бесплатная версия, но мы используем платную, потому что она предоставляет API. Из коробки они нормальные, но мы довели до более приятного вида
* [**Chunky**](https://www.spigotmc.org/resources/chunky.81534/)\
  Плагин на прогрузку чанков
* [**RayTraceAntixray**](https://github.com/stonar96/RayTraceAntiXray)\
  антииксрей с рей-трейсингом. скрывает руды лучше любого  другого плагина. пример работы: [смотреть](https://user-images.githubusercontent.com/18699205/112784731-aed75e00-9052-11eb-92d6-b0dd4af79290.gif)
*   [**EntityDetection**](https://modrinth.com/plugin/entitydetection)

    ищет скопления энтити в мирах
*   [**OreAnnouncer**](https://github.com/AlessioDP/OreAnnouncer)

    логирует вскапывание руд в чат админам и хелперам
*   [**SayanVanish**](https://github.com/Syrent/SayanVanish)

    крутой плагин на ваниш, интегрирован с нашим чатом и табом
*   [**UnifiedMetrics**](https://github.com/Cubxity/UnifiedMetrics)

    собирает метрики с серверов и отправляет в prometheus для алертов и визуализации
*   [**Vulcan**](https://www.spigotmc.org/resources/vulcan-anti-cheat-advanced-cheat-detection-1-7-1-21.83626/)

    самый именитый платный античит на рынке, алертит в дискорд, кики отключены чтобы читеры не узнали что их детектит
*   [**ProtocolLib**](https://github.com/dmulloy2/ProtocolLib)

    библиотека для наших и чужих плагинов чтобы взаимодействовать с протоколами майнкрафта
*   [**packetevents**](https://github.com/retrooper/packetevents)

    библиотека для работы с сетевыми пакетами
*   [**PlaceholderAPI**](https://www.spigotmc.org/resources/placeholderapi.6245/)

    плагин для работы с плейсхолдерами, например таб через papi получает TPS от лакпермса
*   [PAPIProxyBridge](https://github.com/WiIIiam278/PAPIProxyBridge)

    помогает placeholderAPI работать на серверах с прокси
*   [**MCKotlin-Paper**](https://modrinth.com/plugin/mckotlin/version/qFLgFUwi)

    добавляет возможность запускать плагины, написанные на котлине
*   [**CoreProtectTNT**](https://github.com/Ghost-chu/CoreProtectTNT)

    дополнение к CoreProtect, позволяет связывать взрывы с его инициатором: кто заагрил крипера и кто поджег динамит. проект архивирован
*   [**ViewDitanceTweaks**](https://github.com/froobynooby/ViewDistanceTweaks)

    динамически изменяет view distance и simulation distance в зависимости от нагрузки на сервер
*   [**miniplaceholder** ](https://modrinth.com/plugin/miniplaceholders)(Velocity)

    позволяет всему, работающему на прокси использовать компоненты миниплейсхолдеров, из-за них ники серые, ошибки красные, а надпись в табе зеленая
*   [**placeholderapi-expansion**](https://github.com/PlaceholderAPI/PlaceholderAPI) (Velocity)

    плагин чтобы работал тпс в табе



