## Что такое Компоненты Android?

Компоненты Android - это основные строительные блоки приложений, которые позволяют организовать и управлять функциональностью программного обеспечения. 
Они созданы для того, чтобы разработчики могли эффективно разделять задачи и организовывать код, что упрощает создание, поддержку и расширение приложений.

## Какие есть основные компоненты?

Основные компоненты Android-приложения включают четыре ключевых элемента, каждый из которых выполняет свою уникальную роль:

1. Activity (Активити)
2. Service (Сервис)
3. Broadcast Receiver (Приемник широковещательных сообщений)
4. Content Provider (Провайдер контента)

## А поподробнее?

Каждый компонент выполняет свою уникальную роль, обеспечивая взаимодействие с пользователем, выполнение фоновых задач, обработку событий и управление данными. Это позволяет приложениям быть более гибкими и адаптивными к различным условиям работы и требованиям пользователей. Компоненты также способствуют лучшему управлению ресурсами устройства и обеспечивают безопасность, изолируя приложения друг от друга.

*  **Activity (Активити):** \
представляет собой интерфейс пользователя и отвечает за взаимодействие с ним. Каждая экран приложения - это отдельная активити.

*  **Service (Сервис):** \
предназначен для выполнения длительных операций в фоновом режиме, не имея пользовательского интерфейса. Сервисы могут работать даже тогда, когда приложение не активно.

* **Broadcast Receiver (Приемник широковещательных сообщений):** \
принимает и обрабатывает системные или пользовательские события, такие как изменения состояния сети, завершение загрузки, низкий заряд батареи  и тп.

* **Content Provider (Провайдер контента):** \
обеспечивает доступ к данным приложения и позволяет обмениваться данными между различными приложениями через стандартный интерфейс


## Что в заключение?

Все эти компоненты имеют разные зоны ответственности и жизненные циклы, но все они являются точками входа в приложение и должны быть зарегистрированы в файле конфигурации `AndroidManifest.xml`.

**Однако!** В версиях Android (начиная с Android 7.0) рекомендуется не регистрировать `BroadcastReceiver` в манифесте, предпочтительнее использовать динамическую регистрацию `BroadcastReceiver` вместо статической.

Это связано с изменениями в политике безопасности и производительности.

Динамическая регистрация позволяет разработчикам регистрировать приемники непосредственно в коде, что дает больше контроля над их жизненным циклом и позволяет избегать ненужной работы, когда приложение не активно.

Зачем нам чтобы наш приемник был активен даже тогда, когда приложение не используется, если можно зарегистрировать BroadcastReceiver тогда, когда он нам нужен, например в методе `onStart()` активити и отменить регистрацию в `onStop()`, это помогает экономить ресурсы устройства.

Статическая регистрация компонента всё еще возможна, но чаще всего нежелательна.

## Ещё подробнее?

* [О компоненте Activity в андроид](Activity/Компонент%20Activity%20(Активити).md)
* [О компоненте Service в андроид](Service/Компонент%20Service%20(Сервис).md)
* [О компоненте Broadcast Receiver в андроид](Broadcast%20Receiver/Компонент%20Broadcast%20Receiver.md)
* [О компоненте Content Provider в андроид](Content%20Provider/Компонент%20Content%20Provider.md)

## Какие вопросы могли возникнуть?

* [Что за манифест (`AndroidManifest.xml`)?](Манифест%20или%20AndroidManifest.md)
