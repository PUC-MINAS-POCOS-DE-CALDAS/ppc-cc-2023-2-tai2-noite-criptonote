# CriptoNote


## Tela Home
Tela inicial do aplicativo
- adicionar nota ([tela WriteNote](WriteNote))
- ir para arquivos ([tela FileHome](FileHome))
- importar notas
- exportar notas
- ir para configurações ([tela Settings](Settings))
- abrir nota ([tela Code](Code))

## Modal Code
Modal que aparece ao abrir uma nota. Ele pede a senha dessa nota e depois vai para a tela em que ela será lida/editada
- Pega a senha (campo opcional) da nota e vai para [EditNote](EditNote)

## Tela WriteNote
Tela para escrever uma nova nota
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
Tela em que uma nota pode ser lida/editada
- Ao abrir a tela:
    - Se alguma senha foi fornecida, o texto é descriptografado e exibido
    - Se não tem senha, o texto lido do banco de dados é exibido
- Possui os campos para edição (o valor inicial é lido do banco de dados ou descriptografado, confirme item anterior)
    - título (obrigatório)
    - texto (obrigatorio)
- na ação de salvar
    - com senha: criptografa o conteúdo e salva no banco de dados
    - sem senha: salva o conteúdo no banco de dados
- na ação de voltar, pergunta se o usuário quer descartar as modificações
    - cancelar: continua na tela
    - descartar: descarta as alterações e volta para a última tela

## Tela Settings
Possui algumas opções/informações extra
- Possui um botão para exportar/compartilhar o banco de dados dos logs
- Possui uma seção com dados do aplicativo (nome e versão)

## Tela FileHome
Tela inicial da criptografia de arquivo
- Tem uma ação para voltar para a tela anterior
- Tem um botão para criptografar arquivos (escolhe o arquivo e vai para FileCode com a intenção de criptografar)
- Tem um botão para descriptografar arquivos (escolhe o arquivo e vai para FileCode com a intenção de descriptografar)

## Tela FileCode
Tela para criptografar/descriptografar um arquivo escolhido com a senha fornecida, e algumas opções para "configurar" o processo
- Tem uma ação para voltar para a tela anterior
- Tem um campo para mudar o nome do arquivo a ser salvo (obrigatório)
- Tem um campo de senha (obrigatório)
- Tem um campo para escolher se o arquivo original é apagado depois da criptografia/descriptografia
- Tem um botão para cancelar a criptografia/descriptografia do arquivo
- Tem um botão para criptografar/descriptogafar o arquivo

- Na criptografia, a extensão ".cn" é adicionada ao final do arquivo
- Na descriptogradia, a extensão ".cn" é removida do nome do arquivo, se existir
- Ao iniciar a criptografia/descriptografia, um alerta aparece dizendo que o processo foi iniciado
- Durante a criptografia/descriptografia, uma notificação exibe o processo
- Ao final da criptografia/descriptografia, uma notificação avisa se o processo terminou com sucesso ou erro


## Módulo Tema
Contem os códigos de cores usados para construir a interface do aplicativo e distribuí-las pelos componentes

## Módulo Constantes
Contem constantes usadas no aplicativo, como:
- nome
- versão
- extensões de arquivos
- caminho de pastas internas
- caminho de pastas externas
- caminho do banco de dados

## Módulo Data
Contem funções para manipular datas
- pegar data
- pegar hora
- pegar data e hora

## Módulo Armazenamento
Contem funções para gerenciar o armazenamento interno e externo do aplicativo
- criar pastas internas do aplicativo
- criar pastar externas do aplicativo
- renomear arquivo adicionando um sufixo, caso já exista um arquivo com mesmo nome em determinada pasta

## Módulo Log
Contem funções para registrar logs
- info
- aviso
- erro

## Módulo Permissão
Contem funções para requisitar permissões para o sistema
- notificação
- ler do armazenamento externo
- escrever no armazenamento externo

## Módulo Crypto
Contem funções de criptografia
- criptografar string
- descriptografar string
- criptografar arquivo
- descriptografar arquivo


## Banco de dados

### Log
Criar um banco de dados para armazenar logs com a tabela:
    - Log
        - ID
        - Tipo (info, aviso, erro)
        - Mensagem
        - Data e hora

### App
Criar um banco de dados do aplicativo para armazenar as notas com as tabelas:
    - Nota
        - ID
        - Título
        - Data de modificação
        - ID do conteúdo
    - Conteúdo da nota
        - ID
        - texto

### Notas exportadas
Criar um banco de dados do aplicativo para exportação, que será aberto quando necessário, com as tabelas:
    - Nota (mesma que acima)
    - Conteúdo (mesma que acima)


## Componente Input
Criar um component Input

## Componente InputPassword
Criar um componente Input para ser usado específicamente para senhas.
- Adicionar um botão para mostrar/esconder a senha ao lado direito do Input
- Configurar algumas propriedades, que podem ser sobrescritas, para uso com senhas
