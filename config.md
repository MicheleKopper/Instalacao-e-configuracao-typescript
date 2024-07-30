# Instalações

01 - Abrir o terminal e criar o arquivo package.json. Usar o -y para criar o arquivo default (padrão), sem personalização.
O arquivo package.json contém as informações do projeto, como versões, dependências e scripts

```bash
npm init -y

```
02 - Criar arquivo index.ts. Printar o console.log para testar, se o arquivo estiver numa pasta digitar o caminho `node /nomedapasta/index.ts`

```bash
node index.ts
```

03 - No arquivo package.json criar um novo script para facilitar o teste no terminal

```bash
"start": "node index.ts"
```

```bash
npm run start
```

04 - Instalar o typescript como dependência de desenvolvimento

```bash
npm i -D typescript
```

05 - Instalar as tipagens do node

```bash
npm i -D @types/node
```

06 - Instalar o `ts-node-dev` para executar o typescript

```bash
npm i -D ts-node-dev

```




# Configurações tsconfig.json

Criar o arquivo `tsconfig.json`, responsável pelas opções do transpilador typescript

```bash
npx tsc --init
```

Dentro do arquivo `tsconfing.json`, ajustar as seguintes propriedades:

- `Target:` atualizar para uma versão mais recente do ECMASCRIPT `"target": "ES2022"`(utilizar sempre 1 ano anterior do atual)

- Criar uma pasta `src` e colocar o index.ts 

- `rootDir:` descomentar e apontar o caminho onde vão estar os arquivos typescript `./src` 

- Criar uma pasta `dist`
   
- `outDir:` descomentar e apontar o caminho onde os arquivos transpilados javascript vão ser destinados `./dist`

- `"exclude": ["node_modules"]` adicionar no final fora do primeiro {}, inserir vírgula. Garante que não vai transpilar o node modules




# Configurações package.json

Dentro do arquivo `package.json`, ajustar as seguintes propriedades:

- Trocar o nome da main para `"/dist/index.js"`
- Criar o scripts `"build": "tsc"` para converter arquivos typescript em javascript
- Rodar no terminal o comando `npx tsc` para buildar (criar) arquivos javascript automáticamente
- Trocar o nome do script start para `"node ./dist/index.js"`
- Criar o script `"dev": "ts-node-dev --respawn --transpile-only ./src/index.ts"`
- Testar o script usando `npm run dev`


* Criar o arquivo `.gitignore` para o node_modules