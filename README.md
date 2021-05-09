[refs-contributing]: /CONTRIBUTING.md

[refs-about]: /docs/about/readme.md
[refs-motivation]: /docs/about/motivation.md
[refs-motivation-why]: /docs/about/motivation.md#-почему-не-хватает-существующих-решений

[refs-getstarted]: /docs/get-started/readme.md

[refs-concepts]: /docs/concepts/readme.md
[refs-arch]: /docs/concepts/architecture.md
[refs-arch-req]: /docs/concepts/architecture.md#-требования
[refs-arch-problems]: /docs/concepts/architecture.md#%EF%B8%8F-проблемы
[refs-splitting]: /docs/concepts/app-splitting.md
[refs-public-api]: /docs/concepts/public-api.md
[refs-isolation]: /docs/concepts/cross-communication.md
[refs-needs-driven]: /docs/concepts/understanding-needs.md

[refs-knowledges]: /docs/references/knowledge-types.md
[refs-abstractions]: /docs/references/abstractions.md
[refs-abstractions-layers]: /docs/references/abstractions.md#-group-layers

[ext-ubiq-lang]: https://thedomaindrivendesign.io/developing-the-ubiquitous-language
[ext-fdd]: https://github.com/feature-sliced/wiki/tree/rc/feature-driven
[ext-discussions]: https://github.com/feature-sliced/wiki/discussions

# feature-sliced

> `WIP:` Работа над методологией в процессе и окончательный вид *может поменяться*
>
> Пока *не рекомендуется** применять **текущую версию** в рабочих проектах
>
> **только на свой страх и риск*

<!-- 🏅 Add badges -->

<!--
[npm]: https://www.npmjs.com/package/NPM_PACKAGE

[![npm](https://img.shields.io/npm/v/NPM_PACKAGE?style=flat-square)][npm]
[![npm](https://img.shields.io/npm/dw/NPM_PACKAGE?style=flat-square)][npm]
[![npm bundle size](https://img.shields.io/bundlephobia/min/NPM_PACKAGE?style=flat-square)][npm]
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FOWNER%2FREPO&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=true)](https://hits.seeyoufarm.com)
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/OWNER/REPO/WORKFLOW?label=tests&style=flat-square)](https://github.com/OWNER/REPO/actions)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/m/OWNER/REPO?style=flat-square)](https://github.com/OWNER/REPO/commits)
-->

<!-- 🖼️ Add logo / primary image -->
<img src="https://avatars.githubusercontent.com/u/60469024?s=120" align="right" width=120>

<!-- ⚡ Add primary information & features about your repository -->
Методология для проектирования *frontend проектов*, нацеленная [**на разделение приложения согласно бизнес-логике и областям ответственности.**][refs-splitting]

- Обеспечивает [**понятность, контролируемость и адаптивность**][refs-arch-req] архитектуры
- Основана на [**проверенных временем**][refs-motivation-why] практиках проектирования и концепциях
    > `SOLID`, `GRASP`, `DDD`, `Vertical Slices`, `Public API`, `Isolation`
- Предлагает разделять проект согласно [**бизнес-юнитам**][ext-ubiq-lang]

## Motivation

Обычно, подходы построения архитектуры фронтенда от проекта к проекту - [переизобретаются с нуля][refs-motivation], пополняя тем самым ["проектные знания"][refs-knowledges]

> Несмотря на то, что специфика фронтенд-проектов отличается не так значительно

При этом, неверно принятые решения зачастую приводят [к проблемам масштабируемости проекта и команды][refs-arch-problems].

И поэтому - вместо того, чтобы придумывать и документировать это каждый раз - хочется **обобщить опыт и сформировать рабочую, проверенную и задокументированную методологию** для проектирования архитектуры фронтенда.

> Да, практик и паттернов - много *(`SOLID`, `GRASP`, `DDD`, ...)*
>
> Но для фронтенда - [крайне трудно найти][refs-motivation] устоявшиеся и конкретные подходы

## Overview

Методология призвана **упростить и стандартизировать декомпозицию логики для больших и долгоживужих проектов.**

Для этого она вводит ряд [концепций][refs-concepts] и [абстракций][refs-abstractions], на которых *может базироваться* архитектура от проекта к проекту:

- для более **явного распределения бизнес-логики по модулям приложения**
    > Согласно [*скоупу влияния*, *бизнес-ответственности* и *техническому назначению*][refs-splitting]
    >
    > Благодаря этому *архитектура стандартизируется и становится более простой для ознакомления*

- для более **легкой адаптации проекта к возникающим новым условиям**
    > Каждый компонент архитектуры имеет свое назначение и не влияет на другие
    >
    > Благодаря этому *под новые требования можно независимо добавлять / изменять функциональность приложения без непредвиденных последствий*

- для упрощения работы **с тех.долгом и рефакторингом**
    > Каждый модуль является независимым и самодостаточным
    >
    > Благодаря этому *можно переписать его с нуля без неожиданных сайд-эффектов*

- для **масштабирования проекта и команды**
    > Увеличение функциональности ведет к гораздо меньшему усложнению проекта, т.к. вся логика распределена детерминированно и изолированно
    >
    > Благодаря этому *легко добавлять и онбордить новых людей в команду, а также расширять функциональность проекта*

- для **контролируемого переиспользования логики**
    > Каждый модуль имеет свои ограничения и рекоммендации на переиспользуемость согласно [своему слою][refs-abstractions-layers]
    >
    > Благодаря этому *сохраняется баланс между соблюдением принципа `DRY` и возможности кастомизировать логику модуля без оверхедных переопределений*

## Concepts

- [`Public API`][refs-public-api]
- [`Isolation`][refs-isolation]
- [`Needs Driven`][refs-needs-driven]

## Structure

> `WIP:` Нейминг групп временный, и будет определен окончательно ближе к релизу

<details>
<summary>Визуальная схема</summary>

> `WIP:` Схема - представляет лишь **примерное** разбиение проекта по модулям и будет определена окончательно ближе к релизу

![visual_schema](./assets/visual_schema.jpg)

</details>

```sh
└── src/
    ├── app/                    # Layer: Приложение
    |                           #
    ├── processes/              # Layer: Процессы (опционален)
    |   ├── {some-process}/     #     Slice: (н-р процесс CartPayment)
    |   |   ├── lib/            #         Segment: Инфраструктурная-логика (хелперы)
    |   |   └── model/          #         Segment: Бизнес-логика
    |   ...                     #
    |                           #
    ├── pages/                  # Layer: Страницы
    |   ├── {some-page}/        #     Slice: (н-р страница ProfilePage)
    |   |   ├── lib/            #         Segment: Инфраструктурная-логика (хелперы)
    |   |   ├── model/          #         Segment: Бизнес-логика
    |   |   └── ui/             #         Segment: UI-логика
    |   ...                     #
    |                           #
    ├── features/               # Layer: Фичи
    |   ├── {some-feature}/     #     Slice: (н-р фича AuthByPhone)
    |   |   ├── lib/            #         Segment: Инфраструктурная-логика (хелперы)
    |   |   ├── model/          #         Segment: Бизнес-логика
    |   |   └── ui/             #         Segment: UI-логика
    |   ...                     #
    |                           #
    ├── entities/               # Layer: Бизнес-сущности
    |   ├── {some-entity}/      #     Slice: (н-р сущность User)
    |   |   ├── lib/            #         Segment: Инфраструктурная-логика (хелперы)
    |   |   ├── model/          #         Segment: Бизнес-логика
    |   |   └── ui/             #         Segment: UI-логика
    |   ...                     #
    |                           #
    ├── shared/                 # Layer: Переиспользуемые ресурсы
    |   ├── api/                #         Segment: Логика запросов к API
    |   ├── lib/                #         Segment: Инфраструктурная-логика (хелперы)
    |   └── ui/                 #         Segment: UI-логика
    |   ...                     #
    |                           #
    └── index.tsx/              #
```

Подробнее в ["Абстракции методологии"][refs-abstractions] и ["Разбиение приложения"][refs-splitting]

## Further reading

- `Get started` [Введение в методологию][refs-getstarted]
- `About` [О методологии][refs-about]
- `Misc` Прочие материалы
  - *Предыдущие* ответвления методологии: *[feature-slices](https://featureslices.dev/v1.0.html)*, *[feature-driven][ext-fdd]*
  - [Доклад React SPB Meetup #1 - Feature Slices](https://t.me/feature_slices)
  - [Feature Driven Architecture - Oleg Isonen](https://www.youtube.com/watch?v=BWAeYuWFHhs)
  - [A feature based approach to React development](https://ryanlanciaux.com/blog/2017/08/20/a-feature-based-approach-to-react-development/)
  - [Why React developers should modularize their applications?](https://alexmngn.medium.com/why-react-developers-should-modularize-their-applications-d26d381854c1)
  - [How to Organize Your React + Redux Codebase](https://www.pluralsight.com/guides/how-to-organize-your-react-+-redux-codebase)
  - [The Humanizing Work Guide to Splitting User Stories *(aka "Vetical Slices")*](https://www.humanizingwork.com/the-humanizing-work-guide-to-splitting-user-stories/)

<br/>

- `Discussions` [Дискуссии по методологии][ext-discussions]
  > **Здесь обсуждаются и разбираются рельные примеры применения, вопросы, проблемы, идеи методологии**
  >
  > Все это в совокупности влияет на спецификацию, тулкит и в целом - на дальнейшее видение и развитие методологии
  >
  > *Т.е. все, чего пока нет в спецификации/тулките - так или иначе обсуждается в github-discussions*
- `Contributing` **Как можно помочь?**
  - ⭐ Оцените нас на GitHub, если у вас остались положительные впечатления
    > Или если по-вашему этот проект должен развиваться дальше
  - 💫 Ознакомьтесь с нашим [contributing][refs-contributing] гайдом
    > **Важно любое содействие** - от *фидбека* до *участия в самой разработке!*

<!-- 
FIXME: Не удалось нормально justify-content:space-around применить в md
Если есть варики как лучше отступы расставить - welcome :)
-->

<!-- TODO: Добавить ссылки, как доработаем ютуб и твиттер -->

<div align="center">

[![tg](./assets/social_tg.png)](https://t.me/feature_sliced "Телеграм-чат")
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![twitter](./assets/social_twitter.png)](#wip "Twitter (в процессе)")
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![open-collective](./assets/social_opencollective.png)](https://opencollective.com/feature-sliced "OpenCollective профиль")
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![youtube](./assets/social_youtube.png)](#wip "YouTube канал (в процессе)")
</div>
