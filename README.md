# INAPO Lead Collector (этап 1)

Форма «Новый лид» с фото визитки, общий список лидов, выгрузка в Excel, настройки услуг/выставок/гипотез.
Вход по email и паролю. Данные хранятся в Supabase. Если нет связи, лид сохраняется на устройстве и уходит позже.

## Файлы
- `index.html` — всё приложение
- `config.js` — сюда вставляются адрес и ключ Supabase
- `supabase/schema.sql` — таблицы, правила доступа, стартовые данные

## Запуск
1. Supabase: создайте проект (регион Frankfurt / EU), SQL Editor → вставьте `supabase/schema.sql` → Run.
2. Authentication → Sign In / Providers → Email: выключите «Allow new users to sign up» (пользователей добавляете вы). Для старта можно выключить «Confirm email».
3. Authentication → Users → Add user: создайте себя и менеджеров (email + пароль).
4. Сделайте себя админом (SQL Editor): `update public.profiles set role='admin' where id=(select id from auth.users where email='ВАШ_EMAIL');`
5. Project Settings → API: скопируйте Project URL и anon public key в `config.js`.
6. GitHub: создайте репозиторий, загрузите эти файлы. Vercel: Add New → Project → выберите репозиторий → Deploy (настройки по умолчанию, это статический сайт).
7. Откройте адрес Vercel на телефоне, войдите, при первом входе введите своё имя. На iPhone: Поделиться → На экран «Домой», на Android: меню → Добавить на главный экран.
