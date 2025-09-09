🚀 Инструкция по запуску

Скачиваете .zip файл

Установите зависимости (через Swift Package Manager или CocoaPods, в зависимости от настроек проекта).
Минимальный набор:

FirebaseAuth
FirebaseCore
GoogleSignIn

При первом запуске вы увидите экран авторизации. После успешного входа приложение переключится на TabBarController.

🔧 Архитектура

Проект использует упрощённый MVVM:
View (AuthorizationView, MainPageView) — UI через UIKit.
ViewController (AuthorizationViewController, MainPageViewController) — связывает UI с ViewModel.
ViewModel (AuthorizationViewModel) — логика авторизации, сетевые вызовы.
Network layer — реализован внутри ViewModel через URLSession (JSON-RPC запросы).

✅ Что можно улучшить в продакшен-версии

Безопасность
Использовать Keychain для хранения accessToken.
Добавить refresh токенов.
Сетевой слой
Вынести в отдельный NetworkService (например, через URLSession + Combine или Alamofire).
Добавить обработку ошибок и retry-механику.

UI/UX

Skeleton-лоадеры для коллекций.
Локализация строк.
Поддержка тёмной темы.

Архитектура

Добавить координаторы для управления навигацией.
Использовать DI-контейнер (например, Swinject).
Покрыть ключевые сценарии Unit/UI тестами.
