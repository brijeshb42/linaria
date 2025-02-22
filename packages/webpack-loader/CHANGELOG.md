# Change Log

## 5.0.3

### Patch Changes

- @linaria/webpack4-loader@5.0.3
- @linaria/webpack5-loader@5.0.3

## 5.0.2

### Patch Changes

- @linaria/webpack4-loader@5.0.2
- @linaria/webpack5-loader@5.0.2

## 5.0.1

### Patch Changes

- @linaria/webpack4-loader@5.0.1
- @linaria/webpack5-loader@5.0.1

## 5.0.0

### Major Changes

- 88e07613: Rewritten dependecny tree processing with support for wildcard re-exports.
- cb853e14: All processing stages were merged into one generators-based processor. It allows the implementation of more complex workflows to support features like dynamic imports and re-exports.

### Minor Changes

- 9cb4143d: Refactoring of the 1st stage of transformation. It opens the road to processing wildcard reexports.

### Patch Changes

- 2a1e24a0: Upgrade TypeScript to 5.2
- Updated dependencies [f3a4f2a9]
- Updated dependencies [9cb4143d]
- Updated dependencies [88e07613]
- Updated dependencies [2a1e24a0]
- Updated dependencies [cb853e14]
  - @linaria/webpack5-loader@5.0.0
  - @linaria/webpack4-loader@5.0.0

## 4.5.4

### Patch Changes

- @linaria/webpack4-loader@4.5.4
- @linaria/webpack5-loader@4.5.4

## 4.5.3

### Patch Changes

- Updated dependencies [520ba8da]
  - @linaria/webpack5-loader@4.5.3
  - @linaria/webpack4-loader@4.5.3

## 4.5.2

### Patch Changes

- Updated dependencies [1bf5c5b8]
  - @linaria/webpack4-loader@4.5.2
  - @linaria/webpack5-loader@4.5.2

## 4.5.1

### Patch Changes

- @linaria/webpack4-loader@4.5.1
- @linaria/webpack5-loader@4.5.1

## 4.5.0

### Minor Changes

- 16c057df: Breaking Change: Performance Optimization for `styled`

  When a component is wrapped in `styled`, Linaria needs to determine if that component is already a styled component. To accomplish this, the wrapped component is included in the list of variables for evaluation, along with the interpolated values used in styles. The issue arises when a wrapped component, even if it is not styled, brings along a substantial dependency tree. This situation is particularly evident when using `styled` to style components from third-party UI libraries.

  To address this problem, Linaria will now examine the import location of the component and check if there is an annotation in the `package.json` file of the package containing the components. This annotation indicates whether the package includes other Linaria components. If there is no such annotation, Linaria will refrain from evaluating the component.

  Please note that this Breaking Change solely affects developers of component libraries. In order for users to style components from your library, you must include the `linaria.components` property in the library's `package.json` file. This property should have a mask that covers all imported files with components. Here's an example of how to specify it:

  ```json
  "linaria": {
    "components": "**/*"
  }
  ```

### Patch Changes

- af5bb92d: The end of support for Node.js 14. Migration to pnpm 8.
- Updated dependencies [16c057df]
- Updated dependencies [af5bb92d]
  - @linaria/webpack4-loader@4.5.0
  - @linaria/webpack5-loader@4.5.0

## 4.1.17

### Patch Changes

- @linaria/webpack4-loader@4.1.17
- @linaria/webpack5-loader@4.1.17

## 4.1.16

### Patch Changes

- @linaria/webpack4-loader@4.1.16
- @linaria/webpack5-loader@4.1.16

## 4.1.15

### Patch Changes

- @linaria/webpack4-loader@4.1.15
- @linaria/webpack5-loader@4.1.15

## 4.1.14

### Patch Changes

- @linaria/webpack4-loader@4.1.14
- @linaria/webpack5-loader@4.1.14

## 4.1.13

### Patch Changes

- @linaria/webpack4-loader@4.1.13
- @linaria/webpack5-loader@4.1.13

## 4.1.12

### Patch Changes

- @linaria/webpack4-loader@4.1.12
- @linaria/webpack5-loader@4.1.12

## 4.1.11

### Patch Changes

- @linaria/webpack4-loader@4.1.11
- @linaria/webpack5-loader@4.1.11

## 4.1.10

### Patch Changes

- @linaria/webpack4-loader@4.1.10
- @linaria/webpack5-loader@4.1.10

## 4.1.9

### Patch Changes

- @linaria/webpack4-loader@4.1.9
- @linaria/webpack5-loader@4.1.9

## 4.1.8

### Patch Changes

- @linaria/webpack4-loader@4.1.8
- @linaria/webpack5-loader@4.1.8

## 4.1.7

### Patch Changes

- @linaria/webpack4-loader@4.1.7
- @linaria/webpack5-loader@4.1.7

## 4.1.6

### Patch Changes

- @linaria/webpack4-loader@4.1.6
- @linaria/webpack5-loader@4.1.6

## 4.1.5

### Patch Changes

- 2906ec1c: Watch dependencies from cached css files in webpack watch mode.
- Updated dependencies [2906ec1c]
  - @linaria/webpack4-loader@4.1.5
  - @linaria/webpack5-loader@4.1.5

## 4.1.4

### Patch Changes

- @linaria/webpack4-loader@4.1.4
- @linaria/webpack5-loader@4.1.4

## 4.1.3

### Patch Changes

- Updated dependencies [c0bd271a]
  - @linaria/webpack4-loader@4.1.3
  - @linaria/webpack5-loader@4.1.3

## 4.1.2

### Patch Changes

- 008a5d13: Fix webpack crash when an error in Linaria happens. (fixes #1029)
- Updated dependencies [008a5d13]
  - @linaria/webpack4-loader@4.1.2
  - @linaria/webpack5-loader@4.1.2

## 4.1.1

### Patch Changes

- @linaria/webpack4-loader@4.1.1
- @linaria/webpack5-loader@4.1.1

## 4.1.0

### Patch Changes

- @linaria/webpack4-loader@4.1.0
- @linaria/webpack5-loader@4.1.0

## 4.0.0

### Major Changes

- bc0cbeea: A completely new async mode with native support for Vite, Rollup, esbuild and Webpack resolvers.

  BREAKING CHANGES: Despite the fact, that it should be fully compatible with 3.0 and 2.0 branches, the new version of styles evaluator can have some serious bugs which can make your project unbuildable (however, since there is no runtime, if the build is finished successfully, everything will continue work as it was on 2.0 and 3.0). If you face some problems please let us know and we will fix it as soon as possible.

### Patch Changes

- 8be5650d: The repo has been migrated to PNPM and Turborepo
- ea41d440: New package @linaria/tags that contains all abstract logic for tags processors.
- Updated dependencies [ea41d440]
  - @linaria/webpack5-loader@4.0.0
  - @linaria/webpack4-loader@4.0.0

## 3.0.0-beta.21

### Patch Changes

- @linaria/webpack4-loader@3.0.0-beta.21
- @linaria/webpack5-loader@3.0.0-beta.21

## 3.0.0-beta.20

### Patch Changes

- 8be5650d: The repo has been migrated to PNPM and Turborepo
- Updated dependencies
- Updated dependencies [8be5650d]
  - @linaria/webpack5-loader@3.0.0-beta.20
  - @linaria/webpack4-loader@3.0.0-beta.20

# [3.0.0-beta.19](https://github.com/callstack/linaria/compare/v3.0.0-beta.18...v3.0.0-beta.19) (2022-06-03)

### Features

- **babel:** api for custom tags ([#976](https://github.com/callstack/linaria/issues/976)) ([3285ccc](https://github.com/callstack/linaria/commit/3285ccc1d00449b78b3fc74087528cd38cbdd116))
- **babel:** new way for detecting tag imports ([#974](https://github.com/callstack/linaria/issues/974)) ([3305cfb](https://github.com/callstack/linaria/commit/3305cfb0c0f65abdacceeb7e6bad118c59f7d551))

# [3.0.0-beta.18](https://github.com/callstack/linaria/compare/v3.0.0-beta.17...v3.0.0-beta.18) (2022-04-01)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.17](https://github.com/callstack/linaria/compare/v3.0.0-beta.16...v3.0.0-beta.17) (2021-12-27)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.16](https://github.com/callstack/linaria/compare/v3.0.0-beta.15...v3.0.0-beta.16) (2021-12-01)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.15](https://github.com/callstack/linaria/compare/v3.0.0-beta.14...v3.0.0-beta.15) (2021-11-29)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.14](https://github.com/callstack/linaria/compare/v3.0.0-beta.13...v3.0.0-beta.14) (2021-11-05)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.13](https://github.com/callstack/linaria/compare/v3.0.0-beta.12...v3.0.0-beta.13) (2021-09-13)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.12](https://github.com/callstack/linaria/compare/v3.0.0-beta.11...v3.0.0-beta.12) (2021-08-31)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.7](https://github.com/callstack/linaria/compare/v3.0.0-beta.6...v3.0.0-beta.7) (2021-06-24)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.6](https://github.com/callstack/linaria/compare/v3.0.0-beta.5...v3.0.0-beta.6) (2021-06-06)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.5](https://github.com/callstack/linaria/compare/v3.0.0-beta.4...v3.0.0-beta.5) (2021-05-31)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.4](https://github.com/callstack/linaria/compare/v3.0.0-beta.3...v3.0.0-beta.4) (2021-05-07)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.3](https://github.com/callstack/linaria/compare/v3.0.0-beta.2...v3.0.0-beta.3) (2021-04-20)

**Note:** Version bump only for package @linaria/webpack-loader

# [3.0.0-beta.2](https://github.com/callstack/linaria/compare/v3.0.0-beta.1...v3.0.0-beta.2) (2021-04-11)

**Note:** Version bump only for package @linaria/webpack-loader
