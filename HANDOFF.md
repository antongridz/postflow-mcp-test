# Handoff

## Сделано в этой сессии

- Установлены скиллы Emil Kowalski (`npx skills@latest add emilkowalski/skills`) в `.agents/skills/` + симлинки в `.claude/skills/`.
- Индикатор выбора плана Klarna (`.klarna-slider`) больше не гаснет/телепортируется — едет через `transform`, строки выровнены (`grid-auto-rows: 1fr`).
- Общая полировка анимаций (`emil-design-eng`): `ease-out` вместо слабых кривых, `:active` с `scale()` на кнопках, hover под `(hover: hover)`, `prefers-reduced-motion`, `:focus-visible`, убраны `transition: all` и мёртвые keyframes.
- Нижняя горизонтальная grid-линия + плюсики теперь плавно едут (`transform`, 180ms) при переключении Card/Klarna, вместо `setTimeout(…, 350)`-прыжка. Переход держится **постоянно** в CSS (не переключается классом в момент движения) — иначе Safari её просто не анимирует и прыгает.
- Добавлен `.gitignore` (`.DS_Store`, `.vercel`, `node_modules/`), убран `.DS_Store` из индекса (файл на диске остался, физически он тут не нужен).
- Перенесён `@font-face` для `Geist Frozen` из локальной несохранённой правки пользователя в `styles.css:29-36`.

## Текущее состояние

- Ветка: `claude/trusting-faraday-41qnf1`, всё запушено в `origin`, HEAD = `e51c248`.
- Не смерджено в `main` — там всё ещё только `Initial commit` (`ef6cc21`).
- Рабочее дерево чистое.

## Открытые хвосты

- **Мёртвый `<link>` на Switzer** (`index.html:9`) — тянет с Google Fonts шрифт, которого там нет (он на Fontshare). Реально страница рисуется системным sans-serif. Не трогал — не спросили явно.
- **`Geist Frozen` объявлен, но нигде не используется** — ни одного `font-family: 'Geist Frozen'` в CSS. Сам файл `fonts/Geist_tnum_wght400_frozen.woff2` не в репозитории (у пользователя локально). Ждём решения: это замена Switzer или что-то другое.
- **Токены из `docs/tokens.md` не заведены в `:root`** (`--radius-*`, `--space-*`, `--text-*`, `--weight-*`, `--shadow-*`) — значения захардкожены по месту в `styles.css`. Документация врёт про то, что реализовано.
- **Весь JS инлайном** в `<script>` внутри `index.html` (~450 строк) — не вынесен в `app.js`, хотя `.cursor/scratchpad.md` это предполагал.
- **Форма нерабочая** — `novalidate`, CTA `<button type="button">`, нет обработчика submit. Это макет, не чекаут.
- **`.cursor/scratchpad.md`** описывает Task 5 (QA & Polish) как незавершённую — вероятно устарел, не проверял актуальность построчно.

## Project gotchas

- **Git identity в этом окружении**: `user.email=noreply@anthropic.com`, `user.name=Claude` — не трогать, так настроено средой.
- **Push**: `git push -u origin claude/trusting-faraday-41qnf1` — ветка уже трекает origin, обычный `git push` тоже сработает.
- **Ветки**: рабочая — `claude/trusting-faraday-41qnf1`, прод/дефолт — `main`. PR не создавался (не просили).
- **Кэш браузера**: после `git pull` изменения в `styles.css` не видны без **hard reload** (`Cmd+Shift+R`) — статика без версионирования, браузер держит старый CSS.
- **Grid-линии CSS-transition**: не переключать `transition` через класс в тот же момент, когда меняется `transform` — Safari тогда пропускает анимацию целиком и прыгает. Transition должен быть в CSS постоянно, мгновенные корректировки (resize, first paint) — через инлайновый `transition: none` на один тик (см. `setLineY()` в `index.html`).
- **Playwright**: браузер уже стоит в `/opt/pw-browsers/chromium-1194/chrome-linux/chrome`, `npx playwright install` не нужен и не запустится (прокси).
- **`.agents/` и `.claude/skills/`**: симлинки друг на друга, `skills-lock.json` пинит версию — не удалять по отдельности.
