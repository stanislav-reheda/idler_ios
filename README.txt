Fishdom OTA Install — инструкция
=================================

1. Деплой на Cloudflare Pages
   - Создай новый проект на https://dash.cloudflare.com → Pages
   - Загрузи всё содержимое папки ios_ota_install (app.ipa, manifest.plist, index.html)
   - После деплоя получишь домен вида: your-project.pages.dev

2. Замени REPLACE_ME на реальный домен
   В двух файлах нужно заменить REPLACE_ME на твой pages.dev домен:
   - manifest.plist — строка с url (https://REPLACE_ME.pages.dev/app.ipa)
   - index.html — строка с href (https://REPLACE_ME.pages.dev/manifest.plist)
   Замени ДО загрузки или передеплой после замены.

3. Установка на iPhone
   - Открой https://your-project.pages.dev в Safari (только Safari, другие браузеры не поддерживают itms-services)
   - Нажми Install
   - На iPhone появится запрос "your-project.pages.dev would like to install Fishdom" → нажми Install
   - Приложение начнёт загружаться на домашний экран

4. Доверие Enterprise сертификату (первый раз)
   После установки приложение не запустится, пока не доверишь сертификат:
   - Settings → General → VPN & Device Management
   - Найди "PLR Worldwide Sales Limited"
   - Нажми Trust / Доверять
   - Подтверди

5. Важно
   - Ссылка работает ТОЛЬКО в Safari
   - HTTPS обязателен (Cloudflare Pages даёт его автоматически)
   - IPA подписан Enterprise сертификатом — устанавливается на любое устройство без UDID
   - Размер app.ipa может превышать лимит бесплатного плана Cloudflare Pages (25 MB на файл)
     Если так — используй Cloudflare R2 Storage или другой хостинг с HTTPS
