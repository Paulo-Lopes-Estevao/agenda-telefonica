# Agenda telefonica (CLI)
É uma pequena aplicação que agenda contactos telefonicos aplicação escalavel, a medida que vai se adicionando contactos foi contruida com [Vue.js](https://vuejs.org/v2/guide/)


## Configuração do projecto deve primeiro
```
npm install
```

### Compilar para devenvolmento
```
npm run serve
```

### Compilar para produção
```
npm run build
```
### Visualização local
após ter feito o npm run build para vizualização local deve instalar :
```
npm install -g serve
```
a seguir executar o comando
```
serve -s dist
```
## Nota :
```
O distdiretório deve ser servido por um servidor HTTP (a menos que você tenha configurado publicPathum valor relativo), portanto, não funcionará se você abrir dist/index.htmldiretamente pelo file://protocolo. A maneira mais fácil de visualizar sua compilação de produção localmente é usando um servidor de arquivos estáticos Node.js, por exemplo,
```

## Contribuindo

Esse é um projeto livre e você pode contribuir com qualquer coisa: Melhorando o readme, aplicando novas funcionalidades e etc....

### Obs: Faça os commits e os testes antes do pull request.