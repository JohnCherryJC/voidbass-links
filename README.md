# VØIDBASS — готовый сайт ссылок

Статический mobile-first лендинг. Не нужны сборка, backend, npm или сторонние шрифты. Работает без JavaScript. Для локального просмотра откройте index.html в браузере.

## Файлы

- index.html — тексты, ссылки, карточки.
- styles.css — оформление, адаптивность, анимации.
- assets/hero.png — созданный для этого проекта фирменный фон.
- assets/favicon.svg — значок вкладки.
- .nojekyll — отключение обработки Jekyll на GitHub Pages.

Все пути относительные: сайт можно размещать и в корне домена, и в подпапке репозитория.

## Изменение ссылок

Telegram и Instagram уже прописаны в index.html. При смене Telegram измените также ссылку «На связи» в шапке.

TikTok и Авито намеренно не имеют URL и не кликаются. Чтобы включить карточку, найдите соответствующий `<article class="card muted" aria-disabled="true">` и:

1. Замените открывающий тег на `<a class="card" href="ВАШ_РЕАЛЬНЫЙ_URL" target="_blank" rel="noopener noreferrer">`.
2. Замените его закрывающий `</article>` на `</a>`.
3. Удалите `<span class="badge">СКОРО</span>`.
4. Замените «Ссылка появится здесь» на имя аккаунта.
5. Перед закрывающим `</a>` можно добавить `<span class="arrow" aria-hidden="true">↗</span>`.

Не используйте `#` вместо адреса соцсети. Пока адреса нет, оставьте исходную заглушку.

## Бесплатно: GitHub Pages

1. Войдите на GitHub и создайте **публичный** репозиторий, например `voidbass-links` (для бесплатного GitHub Pages).
2. Распакуйте ZIP. Через **Add file → Upload files** загрузите содержимое папки сайта: index.html должен оказаться в корне репозитория, рядом со styles.css и папкой assets. Не загружайте сам ZIP вместо файлов. Сохраните изменения (**Commit changes**).
3. Откройте **Settings → Pages**.
4. В **Build and deployment → Source** выберите **Deploy from a branch**.
5. Укажите ветку **main**, папку **/ (root)** и нажмите **Save**.
6. Дождитесь завершения публикации. Адрес появится в разделе Pages; обычно он имеет вид `https://ВАШ_ЛОГИН.github.io/voidbass-links/`.
7. Меняйте файлы в этой ветке, чтобы обновлять сайт. Если обновление не видно, дождитесь завершения задания Pages и обновите страницу без кеша.

Документация: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Бесплатно: Cloudflare Pages — загрузка без Git

1. Войдите в Cloudflare Dashboard, откройте **Workers & Pages**.
2. Выберите создание приложения/проекта **Pages**, затем **Direct Upload / Drag and drop your files** (названия кнопок могут немного отличаться).
3. Задайте свободное имя проекта.
4. Загрузите этот ZIP или распакованную папку сайта. В корне загружаемых файлов должен быть index.html.
5. Нажмите **Deploy site** и дождитесь статуса успешного размещения. Cloudflare выдаст адрес на `pages.dev`.
6. Для обновления создайте новый deployment в том же проекте и загрузите обновлённые файлы.

Для Direct Upload нет команды сборки и не нужен сервер. У Cloudflare Pages есть бесплатный тариф с лимитами; собственный домен покупать для запуска не нужно. Direct Upload проект нельзя позднее переключить на Git integration — для этого понадобится новый проект.

Документация: https://developers.cloudflare.com/pages/get-started/direct-upload/

## Проверка и особенности

- Проверены наличие локальных ресурсов, якоря, точные адреса двух соцсетей и отсутствие URL у заглушек.
- Адаптивные режимы: одна колонка карточек на телефоне, две от 650 px; размеры заголовка меняются плавно.
- Есть видимый фокус клавиатуры, ссылка пропуска к карточкам и режим prefers-reduced-motion.
- Все ресурсы локальные; внешние запросы нужны только при переходе в соцсеть.
- Автоматический браузерный предпросмотр заблокирован политикой среды для локальных файлов. Визуальная проверка в браузере и реальное открытие внешних профилей не выполнены. Перед публикацией откройте index.html на телефоне и компьютере и проверьте переходы.

## Графика

Фон создан встроенной генерацией изображений OpenAI для VØIDBASS. Использованный промпт:

> Use case: ads-marketing. Create a premium aggressive car-audio brand website hero background, landscape 1536x1024. Extreme close-up of a massive black subwoofer cone on the right, sculptural concentric rubber and brushed black metal, red rim lighting, deep black studio background, subtle crimson haze and fine airborne dust, diagonal red laser slash. Left half mostly dark negative space for HTML lettering. Photorealistic high-end product campaign, very dramatic contrast. No text, no logos, no watermark. Intended for VØIDBASS black/red visual identity.
