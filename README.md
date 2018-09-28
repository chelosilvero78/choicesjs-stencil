# Choices Web Component

Select Web Component. It just wraps [Choices.js][choicesjs] library using StencilJS.

The Select component allows a user to select from dropdowns, browser between multiple options, add tags to an input, etc...

This is a real [_Web Component_][web-component] which has been created with [_StencilJS_ library][stenciljs].

It is written using [_Typescript_][typescript] with [_JSX_][jsx].

## Use cases

The purpose of this project is to create a simple Web Component wrapper from the [Choices.js][choicesjs] library.

All the available use cases of the original library can be perform using this Web Component.

For more information read the [library documentation][choicesjs-documentation].

## Requirements and dependencies

[NodeJS and NPM][node] are required to work with the repository.

The library is based on [Choices.js][choicesjs], but it is not bundle along with the wrapper. It has been defined as part of [`peerDependencies`][peer-dependencies], therefore it has to be included in your own `dependencies`.

This dependency can be added to the bundle as external library, or it can just be added to the page via CDN script:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/choices.js/3.0.4/choices.js"></script>
```

## Installation and running

This component is available via NPM.

```
npm install choicesjs-stencil
```

Include the component in your application via HTML script:

```html
<script src="choicesjs-stencil/dist/choicesjsstencil.js"></script>
```

Use it as a new HTML element in your template:

```html
<choicesjs-stencil values="foo, bar"></choicesjs-stencil>
```

The component is also available as module to be loaded via module bundler:

```javascript
require('choicesjs-stencil');
```

### Advanced usage

Some of this component properties must be set via JavaScript (non primitive types). As well as properties, the component provides public methods and events (see the [library documentation][choicesjs-documentation]).

```html
<choicesjs-stencil type="single"></choicesjs-stencil>

<script>
  var element = document.querySelector('choicesjs-stencil');

  element.choices = [
    {
      value: '',
      label: 'Pick an item...',
      placeholder: true
    }, {
      value: 'foo',
      label: 'Foo'
    }, {
      value: 'bar',
      label: 'Bar'
    }, {
      value: 'qux',
      label: 'Qux'
    }
  ];

  element.disable();
</script>
```

### Configuration

- `type`: the type of selector to render, defaults to `text`. Options: `text`, `single`, `multiple`.
- `items`: a list of preselected values for `text` type select. It must be set via JavaScript.
- `choices`: a list of available values for `single` and `multiple` type selects. It must be set via JavaScript.

Additionally, more options can be set, check the [documentation][choicesjs-documentation] for further details.

### Browser support

Chrome (and all Chrome based browsers), Safari, Firefox and Edge (IE11 is also supported).

### Static example

Open `index.html` file after running `npm run build`.

## Development

To contribute to this project it is necessary to work with NodeJS v8 or later.

Install dependencies:

```
npm install
```

### Building

Run `npm run build` to build the minified version (the same as `npm run build:min`).

Also, if you want to work with the library and have it live built, you can run `npm run build:dev` which creates a live server ready to be used: `http://localhost:3333/`.

The example is located in `src/index.html`.

### Dev server

The development server is included:

```
npm run start
```

### File structure

```
<rootDir>/
├── dist/                   (distribution folder)
├── docs/                   (generated documentation)
├── [example]/              (files to use the public demo)
├── src/                    (sources folder)
│  ├── components/          (folder with the different components)
│  │   └── [name]/          (folder for a component)
│  ├── [components.d.ts]    (autogenerated file with types for the components)
│  └── index.html           (dev index)
├── test/                   (test folder)
│   ├── specs/              (test scripts)
│   │   └── TEST-TYPE/
│   └── results/            (test results)
│       └── TEST-TYPE/
├── [www]/                    (autogenerated dev server directory)
├── index.html              (public demo)
├── jest.config.js
├── stencil.config.js
├── tsconfig.json
├── tslint.json
├── package.json
├── README.md
└── ...
```

### Testing

[Jest][jest] is the test tool, it is run via scripts:

- Tests: `npm run test`
  - Run by type: `npm run test:TYPE`
- Test coverage: `npm run test:coverage`
  - Run by type: `npm run test:coverage:TYPE`

Test results found in `tests/results/TYPE/coverage` folder.

### Code linting

- Lint sources files (TS, TSX): `npm run lint`

### Documentation

Generate documentation with [_typedoc_][typedoc]: `npm run doc`

Documentation found in `docs` folder.

## FAQ

### Maintainers

Check the contributor list and you will be welcome if you want to contribute.

### Contributing

Check out the [CONTRIBUTING.md](.github/CONTRIBUTING.md) to know how to contribute to this project.

## License and Software Information

© adidas AG

adidas AG publishes this software and accompanied documentation (if any) subject to the terms of the MIT license with the aim of helping the community with our tools and libraries which we think can be also useful for other people. You will find a copy of the MIT license in the root folder of this package. All rights not explicitly granted to you under the MIT license remain the sole and exclusive property of adidas AG.

NOTICE: The software has been designed solely for the purpose of wrapping the ChoicesJS library as Web Component. The software is NOT designed, tested or verified for productive use whatsoever, nor or for any use related to high risk environments, such as health care, highly or fully autonomous driving, power plants, or other critical infrastructures or services.

If you want to contact adidas regarding the software, you can mail us at _opensourcesoftware@adidas.com_.

For further information open the [adidas terms and conditions][terms-and-conditions] page.

### License

[MIT](LICENSE)

[choicesjs]: https://github.com/jshjohnson/Choices
[choicesjs-documentation]: https://github.com/jshjohnson/Choices/tree/master
[jest]: https://jestjs.io/
[jsx]: https://jsx.github.io/
[peer-dependencies]: https://docs.npmjs.com/files/package.json#peerdependencies
[stenciljs]: https://stenciljs.com
[typedoc]: http://typedoc.org/
[typescript]: http://www.typescriptlang.org/
[web-component]: https://www.webcomponents.org/
