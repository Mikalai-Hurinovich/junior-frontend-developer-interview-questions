# Содержание

- [Уроки](#Уроки)
- [Переменные](#Переменные)
- [Lifecycle](#Lifecycle)
- [Data binding](#Data-binding)
- [Directives](#Directives)
- [Components](#Components)
- [Store Managment](#Store-Managment)

## Уроки

### Angular

1. Быстрый старт:
    - [Code craft - quick start - 2019 - Eng.][ACodeCraft]
    - [Traversy Media - Crash Course - 2019 - Eng.][ACrashCourse]
2. Начало работы:
    - [Scrimba - get started - 2018 - Eng.][AScrimba]
    - [Egghead - get started - 2017 - Eng.][AEggheadAngular]
3. Оффлайн:
    - [Udemy from torrent - 2018 - Eng.][AUdemy]
4. Вопросы к собесу:
    - [Angular interview questions - RU][AGithubRu]
5. Рекомендуемые ссылки:
    - [Angular RU][ARu]

[ARu]: https://github.com/Angular-RU
[AUdemy]: https://rutracker.org/forum/viewtopic.php?t=5534170
[AScrimba]: https://scrimba.com/g/gyourfirstangularapp
[AGithubRu]: https://github.com/Angular-RU/angular-ru-interview-questions
[ACodeCraft]: https://codecraft.tv/courses/angular/quickstart/overview/
[ACrashCourse]: https://www.youtube.com/watch?v=Fdf5aTYRW0E
[AEggheadAngular]: https://egghead.io/lessons/angular-say-hello-world-to-angular-2

### AngularJS

1. Быстрый старт:
2. Начало работы:
    - [Egghead - get started - 2017 - Eng.][AEggheadAngularJS]
3. Оффлайн

[AEggheadAngularJS]: https://egghead.io/lessons/angularjs-introduction-to-building-an-angularjs-app

## Переменные

```html
<h2 #p2>Some text</h2>
<form #f="ngForm">
    <button [disable]="!f.form.valid">Button</button>
</form>

```

## Lifecycle

Порядок выполнения "хуков" сохранен

- `NgOnChanges` - срабатывает каждый раз когда меняется `Input` проперти когда мы передаем в нашу компоненту. Вызывается перед `NgOnInit`
- `NgOnInit` - срабатывает один раз при после `NgOnChanges` и иинициализует какие-то данные, т.к. работает с данными (вызывает сервисы).
- `NgDocheck` - в отличии от `NgOnChnages` он отрабатывает при каждом прогоне `NgOnAction`??? Например: есть форма, при каждом измении каждого элемента будет вызывать `NgDoCheck` - это доргая операция и имеет смысл при кастомных валидациях
- `NgAfterContentInit` -
- `NgAfterContentChecked` -
- `NgAfterViewInit` -
- `NgAfterViewChecked` -
- `NgOnDestroy` -  используется перед тем как Ангуляр уничтожит компоненту. Используется для уничтожения всяких евентов и т.д. Чтобы обезопасить себя на `memory leaks`.

## Data binding

- `{{property}}` - Интерполяция - example: `<p>{{message}}</p>`;
- `[]="property"` - Property Binding - example: `<h2 [textContent]="message"><h2>`
- `()="method()"` - Event Binding - example: `<button (click)="sayHello()">Say hello</button>`;
- `[(ngModel)]="property"` - Two Way Binding
  - example: `<input [(ngModel)]="username"`;
  - bannas in the box
  - It's = `[ngModel]="username" (ngModelChange)="...."`

Questions:

- Что такое NgModel?

## Directives

## Guard

## Pipe

## Module

## Components

- `Компоненты` - это "строительные"  блоки UI в приложении. Они простым TS классом и это декоратор который представляет собой набор мета информации о классе. Он наследуется от `Directive`.

- `Component` vs `Directive` - всегда есть `teamplate` ( `teamplateUrl` or `teamplate`)

- `Component Methods` - Определяеют его поведение
- `Component Methods` - Определяеют его состояние

### Content of Components

- `ng-content` - если из какой-то внешней компоненты вызываем нашу мы можем передать кусок разметки
- `ng-template` -
- `ng-`

## Components Metadata

- `animation` - list of animation of this components
- `changeDetection` -
- `encapsultaion` - Говорит о том, как мы обрабатывать текущие компонент (!)
- `entryComponents` -
- `interpolation` - заменяется обычный кавычки для интеполяции. Example: `[}}, {{]` -> `}}property{{`
- `moduleId` - можно переопределить модуль в котором он будет использоваться, плохая штука
- `template` - inline HTML
- `templateUrl` - относительный путь к шаблоны
- `styles` - inlint Styles
- `styleUrls` - относительный путь к стилям
- `viewPropviders` -

Унаследовано от Directives:

- `* exportAs` -
- `* host` -
- `* input` -
- `* outputs` -
- `* providers` - Своего рода синглотн для компоненты. При каждом обьявлении нового компонента будет создан новый синглотон. Что является `V8 killers`
- `* queries` -
- `* selector` -

## Decorators

- `@Input` - связавыает родителя и дете
- `@Output` - не поддерживает bubling

## Smart and Dump Components

По-сути пришли с React

### Smart

- Жестко привязанны к нашему приложению
- используют какие-то сервисы
- call to back-end
- Работают с данными
- Обычно связаны с `Service(s)` этого компонента

### Dump or Presentation Components

- Не имеют внутренной логики
- Реюзабельны
- Их поведение определяется теми св-вами которыми мы в них передаем

## Templates

```html

```

## Router

## Service

## Store Managment

### Flux

- Концепция Flux
![Angular flux schema][AFlux-schema-image]

[AFlux-schema-image]: ./img/angular-flux.jpg

### Redux

- Flux vs Redux
![Angular flux vs redux][AFlux-vs-redux-schema-image]

- Концепция Redux
![Angular redux schema][ARedux-schema-image]

- Дополнительно:
  - [Angular RU: Flux, Redux, NgRx, NgXs, Akita - RU][AGithubRu-Redux]

[ARedux-schema-image]: ./img/angular-redux.jpg
[AGithubRu-Redux]: https://www.youtube.com/watch?v=sxN5hmb2hdU
[AFlux-vs-redux-schema-image]: ./img/angular-flux-vs-redux.jpg

### NgRx

`NgRx` - Redux + RxJs + Angular

- Концепция NgRx
![Angular NgRx schema][ANgRx-schema-image]

Дополнительные:

- [Серия видео, Angular 4, RU][ANgRxCoursehunters]
- [Серия видео, ENG][ANgRxToddMotto]

[ANgRxToddMotto]: https://www.youtube.com/watch?v=N_UQx8dPPkc&list=PLW2eQOsUPlWJRfWGOi9gZdc3rE4Fke0Wv
[ANgRx-schema-image]: ./img/angular-ngrx.jpg
[ANgRxCoursehunters]: https://coursehunters.net/course/angular-4-ngrx
