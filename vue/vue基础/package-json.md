```java
{
  "name": "your-project-name",
  "version": "0.1.0",
  "scripts": {
    "clean": "rm -rf node_modules",
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint --no-fix",
    "stylelint": "stylelint src/**/*.{scss,css,less,css,vue,jsx} --fix",
    "eslint": "eslint --ext .js,.jsx,.vue src --fix",
    "changelog": "conventional-changelog -p angular -i CHANGELOG.md -s -r 0"
  },
  "repository": {
    "type": "git",
    "url": "http://gitlab.transsion.com/mi/mi-bigdata-admin.git"
  },
  "dependencies": {},
  "devDependencies": {
    "@commitlint/cli": "^8.1.0",
    "@commitlint/config-conventional": "^8.1.0",
    "babel-eslint": "^10.0.1",
    "conventional-changelog-cli": "^2.0.23",
    "eslint": "^6.2.1",
    "eslint-plugin-vue": "^5.2.3",
    "husky": "^3.0.4",
    "lint-staged": "^9.2.3",
    "stylelint": "^10.1.0",
    "stylelint-config-standard": "^18.3.0",
    "stylelint-scss": "^3.9.4",
  },
  "gitHooks": {
    "pre-commit": "lint-staged"
  },
  "lint-staged": {
    "*.{js,vue}": [
      "vue-cli-service lint",
      "eslint --fix --ext .js,.vue src",
      "git add"
    ],
    "*.{css,scss,less,vue}": [
      "stylelint --fix",
      "git add"
    ]
  },
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}

```