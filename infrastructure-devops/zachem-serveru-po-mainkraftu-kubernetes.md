---
hidden: true
---

# Зачем серверу по майнкрафту Kubernetes?

## Предыстория

В первые месяцы разработки проекта у нас была всего одна хост-машина, ничего необычного. Использовали [Portainer](https://www.portainer.io/), в который заливали [docker-compose](https://docs.docker.com/compose/) файлы и радовались жизни.&#x20;

Через некоторое время встал вопрос о двух средах: дев и прод. Первый будет объединять тестовую инфраструктуру, получать свежие обновления, тестировать их. Второй же – основной – которым будет пользоваться основная масса игроков. Обновления будут выходить реже, проходить тестирование и ревью. Это привело нас к покупке второй хост-машины.&#x20;

Ставить два Портейнера и полностью разделять две среды? А как же CI/CD? А как же удобное администрирование? Автоматизация? Ведь с самого начала, мы, как команда разработчиков, должны были в первую очередь обустроить себе комфортную среду обитания, чтобы с головой уйти в разработку и не думать про инфраструктурные моменты, ведь они занимают такое огромное количество времени и сил. Пришли к выводу – разворачиваем [Kubernetes](https://kubernetes.io/).&#x20;

## Как Kubernetes покрывает наши потребности?

Любой хороший в техническом плане майнкрафт проект будет наворочен разным функционалом: разделение на миры, автоматические перезапуски, резервное копирование, сложная автоматизация процессов деплоя нового функционала и прочим. Kubernetes позволяет нам легко и удобно администрировать наши ресурсы, распределяя их по машинам, предоставляет мощные инструменты для мониторинга и конфигурации. Да и просто прикольно использовать настолько мощные инструменты.

