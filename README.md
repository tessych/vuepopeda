# Вьюпобеда.рф

Рофл-сайт на Vue.js: Vue логотип атакует React логотип, ниже список союзных сайтов победы.

## Локально

```bash
npm install
npm run dev
```

## Сборка

```bash
npm run build
```

Готовая статика появляется в `dist`.

## GitHub Pages

В репозитории уже есть workflow `.github/workflows/deploy.yml`. Он собирает Vite-проект и публикует `dist` в GitHub Pages при пуше в ветку `main`.

Для домена `вьюпобеда.рф` в настройках GitHub Pages укажи punycode-версию:

```text
xn--80abcje6cg7hsa.xn--p1ai
```

У DNS-провайдера для apex-домена обычно нужны `A`-записи GitHub Pages:

```text
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

После привязки домена в GitHub Pages включи HTTPS, когда GitHub выпустит сертификат.
