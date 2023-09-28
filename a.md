# CriptoNote


## Tela Home
- adicionar nota ([tela WriteNote](WriteNote))
- ir para arquivos ([tela FileHome](FileHome))
- importar notas
- exportar notas
- abrir nota ([tela Code](Code))

## Modal Code
- Pega a senha (campo opcional) da nota e vai para [EditNote](EditNote)

## Tela WriteNote
- Possui os campos
    - título (obrigatório)
    - senha (opcional)
    - texto (obrigatorio)
- na ação de salvar:
    - se não tem senha: a nota é salva sem criptografia no banco de dados
    - se tem senha: a nota é criptografada, e depois salva no banco de dados
- na ação de voltar, pergunta se o usuário quer descartar a nota ou não
    - cancelar: continua na tela
    - descartar: descarta a nota e volta para a última tela

## Tela EditNote
- Ao abrir a tela:
    - Se alguma senha foi fornecida, o texto é descriptografado e exibido
    - Se não tem senha, o texto lido do banco de dados é exibido
- Possui os campos para edição
    - título (obrigatório)
    - texto (obrigatorio)
- na ação de salvar
    - com senha: criptografa o conteúdo e salva no banco de dados
    - sem senha: salva o conteúdo no banco de dados
- na ação de voltar, pergunta se o usuário quer descartar as modificações
    - cancelar: continua na tela
    - descartar: descarta as alterações e volta para a última tela

## Tela Settings
- Possui um botão para exportar/compartilhar o banco de dados dos logs
- Possui uma seção com dados do aplicativo (nome e versão)

## Tela FileHome
- Tem um botão para escolher arquivos para criptografar
- Tem um botão para escolher arquivos para descriptografar

## Tela FileCode
- Tem um campo para mudar o nome do arquivo a ser salvo (obrigatório)
- Tem um campo de senha (obrigatório)
- Tem um campo para escolher se o arquivo original é apagado depois da criptografia/descriptografia
- Tem um botão para cancelar a criptografia/descriptografia do arquivo
- Tem um botão para criptografar/descriptogafar o arquivo


## Módulo Crypto
Contem funções de criptografia
- criptografar string
- descriptografar string
- criptografar arquivo
- descriptografar arquivo

