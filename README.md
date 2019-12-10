# Bem-vindo ao tutorial de iniciação de projetos React-Native

Este tutorial visa padronizar a criação de projetos React-Native na empresa onde eu trabalho.
Esta padronização é importante para garantir um padrão de qualidade ao iniciar novos projetos, dessa forma, independentemente do desenvolvedor que irá por a mão na massa neste projeto, saberá por onde começar. Além disso, com isso podemos padronizar o **style-code** dos projetos, ou seja, códigos estarão sempre padronizados também!


## Iniciando o projeto

Para iniciar o projeto, basta instalar o React-Native na máquina e executar o comando:
> *npx react-native init **nome-do-projeto***

## Garantindo o Code Style

Garantir o estilo padrão dos códigos é importante para qualquer empresa que preza pela qualidade dos códigos, e além disso, quando qualquer desenvolvedor for mexer em códigos de outros a padronização é mantida.
Para garantir e até mesmo forçar os desenvolvedores a manter o code style podemos utilizar algumas ferramentas que podem nos ajudar e que integram muito bem com o React-Native.
Para instalar os pacotes que forçam a manter o padrão é só copiar o código abaixo para instalar com o NPM:

> npm install eslint prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D


**.EditorConfig:**
Com o editor config podemos garantir algumas regras de padrão de código independentemente do Editor/IDE que o desenvolvedor está utilizando.
>root = true
  [*]
  end_of_line = lf
 indent_style = space
 indent_size = 2
 charset = utf-8
 trim_trailing_whitespace = true
 insert_final_newline = true

**ESLint**
Para configurar o ESLint, basta seguir o passo-a-passo abaixo:
>npx eslint --init

Feito isso o ESLint irá mostrar diversas opções, então, basta selecionar as opções como o passo-a-passo abaixo:
>- To check syntax, find problems, and enforce code style
>- Javascript modules (import/export)
>- React
>- Use a popular style guide
>- Airbnb
>- Javascript

Após isso, edite o arquivo *.eslintrc.js* como abaixo:
> module.exports = {
		env: {
			es6: true,
			jest: true,
			browser: true,
		},
		extends: ['airbnb', 'prettier', 'prettier/react'],
		globals: {
			Atomics: 'readonly',
			SharedArrayBuffer: 'readonly',
			__DEV __: true,
		},
		parserOptions: {
			ecmaFeatures: {
				jsx: true,
			},
			ecmaVersion: 2018,
			sourceType: 'module',
		},
		plugins: ['react', 'jsx-a11y', 'import', 'react-hooks', 'prettier'],
		rules: {
			'prettier/prettier': 'error',
			'react/jsx-filename-extension': ['error', {extensions: ['.js', '.jsx']}],
			'import/prefer-default-export': 'off',
			'no-unused-vars': ['error', {argsIgnorePattern: '^_'}],
			'react/jsx-one-expression-per-line': 'off',
			'global-require': 'off',
			'react-native/no-raw-text': 'off',
			'no-param-reassign': 'off',
			'no-underscore-dangle': 'off',
			camelcase: 'off',
			'no-console': ['error', {allow: ['tron']}],
			'react-hooks/rules-of-hooks': 'error',
			'react-hooks/exhaustive-deps': 'warn',
			'react/jsx-props-no-spreading': 'off',
			'react/require-default-props': 'off',
			'react/state-in-constructor': 'off',
			'react/static-property-placement': 'off',
			'react/prop-types': ['error', {ignore: ['navigation']}],
		},
		settings: {
			'import/resolver': {
				'babel-plugin-root-import': {
					rootPathSuffix: 'src',
				},
			},
		},
	};

