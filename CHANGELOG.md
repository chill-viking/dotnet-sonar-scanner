# Changelog

## [2.0.2](https://github.com/chill-viking/dotnet-sonar-scanner/compare/v2.0.1...v2.0.2) (2023-01-13)


### Bug Fixes

* **ci:** update test workflow to run on push ([e003626](https://github.com/chill-viking/dotnet-sonar-scanner/commit/e0036265b04adc86a91fa9c22f84622947cb0e94))

## [2.0.1](https://github.com/chill-viking/dotnet-sonar-scanner/compare/v2.0.0...v2.0.1) (2022-12-21)


### Bug Fixes

* **workflow:** drop command parameter ([751205d](https://github.com/chill-viking/dotnet-sonar-scanner/commit/751205d844f19b1e0b1186fddb0ca8e869d3919a))
* **workflow:** update workflow to tag releases ([001a06d](https://github.com/chill-viking/dotnet-sonar-scanner/commit/001a06dd307a413c63332b0b78ffe1ae687db230))

## [2.0.0](https://github.com/chill-viking/dotnet-sonar-scanner/compare/v1.0.0...v2.0.0) (2022-12-02)


### ⚠ BREAKING CHANGES

* **action:** change token inputs

### Features

* **action:** add `checkout` input for action ([d991b92](https://github.com/chill-viking/dotnet-sonar-scanner/commit/d991b925f00fa7a31cbb267a51e4f1c3c86c2ef9))
* **workflow:** add workflow to test action is functioning ([88052a4](https://github.com/chill-viking/dotnet-sonar-scanner/commit/88052a44b13ce5c03c86a712aa312b4162557a74))


### Bug Fixes

* **action:** use correct input properties in action ([a7fc8fc](https://github.com/chill-viking/dotnet-sonar-scanner/commit/a7fc8fc8d697827b58ff077ce0e50591e395c49f))
* **workflow:** pass ref from PR to test workflow ([de709e4](https://github.com/chill-viking/dotnet-sonar-scanner/commit/de709e4450d4a3a0ebf9d89939f012f56a11fb5f))
* **workflow:** update github-script usage ([2f4e55f](https://github.com/chill-viking/dotnet-sonar-scanner/commit/2f4e55f165bbed565c4076f935345cb1feb1d696))
* **workflow:** use json-to-variables ([0ec51ad](https://github.com/chill-viking/dotnet-sonar-scanner/commit/0ec51ad56e0da98c08d434216bf5f39520df0dae))
* **workflow:** use suggested output setter ([c407fca](https://github.com/chill-viking/dotnet-sonar-scanner/commit/c407fca8f62ac5455a56f9453f6dcf3b052a00e8))


### Code Refactoring

* **action:** change token inputs ([89350b7](https://github.com/chill-viking/dotnet-sonar-scanner/commit/89350b7436afb9e4c905ff64f6be0a3923dad588))

## 1.0.0 (2022-11-29)


### Features

* **action:** create dotnet-sonar-scanner ([cd8fac2](https://github.com/chill-viking/dotnet-sonar-scanner/commit/cd8fac22a9f5f63733a2a29fc0bae05a98020e11))


### Bug Fixes

* **action:** adjust directory separator ([725d5a5](https://github.com/chill-viking/dotnet-sonar-scanner/commit/725d5a5d92094353fdb90f12eb4c91a227825270))
* **action:** specify correct path for dotnet-sonarscanner ([9747b14](https://github.com/chill-viking/dotnet-sonar-scanner/commit/9747b14ab82bf8bedae1082031e3db3905d4457f))
* **action:** specify working-directory for build step ([5eb991d](https://github.com/chill-viking/dotnet-sonar-scanner/commit/5eb991d757d4f498a65a668910694ede06fbda94))
* **action:** update actions/setup-dotnet action to v3 ([#6](https://github.com/chill-viking/dotnet-sonar-scanner/issues/6)) ([b3d5e7b](https://github.com/chill-viking/dotnet-sonar-scanner/commit/b3d5e7b9d836d600ced0d3721cdf5fe982844b51))
