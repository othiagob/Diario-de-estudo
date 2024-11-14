# Documentação AstroNvim - Comandos em Português

## Introdução
O AstroNvim geralmente utiliza comandos baseados na tecla `<Leader>`, que por padrão está configurada como `<Space>` (tecla de espaço). O plugin which-key.nvim é usado para fornecer ajuda na descoberta e memorização desses comandos. Basta pressionar uma tecla como `<Space>` e um menu de ajuda aparecerá com menus e opções rotuladas.

## Comandos Gerais
| Ação | Comando | Explicação |
|------|---------|------------|
| Tecla Leader | Espaço | Tecla principal para iniciar a maioria dos comandos |
| Tecla Leader Local | , (vírgula) | Tecla alternativa para comandos específicos de contexto |
| Redimensionar para Cima | Ctrl + Seta Cima | Aumenta o tamanho da janela atual verticalmente |
| Redimensionar para Baixo | Ctrl + Seta Baixo | Diminui o tamanho da janela atual verticalmente |
| Redimensionar para Esquerda | Ctrl + Seta Esquerda | Diminui o tamanho da janela atual horizontalmente |
| Redimensionar para Direita | Ctrl + Seta Direita | Aumenta o tamanho da janela atual horizontalmente |
| Janela Superior | Ctrl + k | Move o cursor para a janela acima |
| Janela Inferior | Ctrl + j | Move o cursor para a janela abaixo |
| Janela Esquerda | Ctrl + h | Move o cursor para a janela à esquerda |
| Janela Direita | Ctrl + l | Move o cursor para a janela à direita |
| Forçar Salvar | Ctrl + s | Salva o arquivo atual mesmo se não houver mudanças |
| Forçar Sair | Ctrl + q | Fecha o editor sem salvar alterações |
| Novo Arquivo | Leader + n | Cria um novo arquivo em branco |
| Fechar Buffer | Leader + c | Fecha o buffer atual |
| Próxima Aba | ]t | Vai para a próxima aba do Vim |
| Aba Anterior | [t | Volta para a aba anterior do Vim |
| Comentar | Leader + / | Comenta/descomenta a linha ou seleção atual |
| Divisão Horizontal | \ | Divide a janela horizontalmente |
| Divisão Vertical | \| | Divide a janela verticalmente |

## Gerenciamento de Buffers
| Ação | Comando | Explicação |
|------|---------|------------|
| Próximo Buffer | ]b | Move para o próximo buffer aberto |
| Buffer Anterior | [b | Move para o buffer anterior |
| Mover Buffer para Direita | >b | Move o buffer atual uma posição para a direita |
| Mover Buffer para Esquerda | <b | Move o buffer atual uma posição para a esquerda |
| Navegar para Buffer | Leader + bb | Abre um seletor interativo de buffers |
| Fechar Todos Exceto Atual | Leader + bc | Fecha todos os buffers exceto o atual |
| Fechar Todos os Buffers | Leader + bC | Fecha todos os buffers abertos |
| Deletar Buffer | Leader + bd | Abre seletor para escolher qual buffer deletar |
| Fechar Buffers à Esquerda | Leader + bl | Fecha todos os buffers à esquerda do atual |
| Buffer Anterior | Leader + bp | Volta para o buffer anterior |
| Fechar Buffers à Direita | Leader + br | Fecha todos os buffers à direita do atual |

## Completação e Snippets
| Ação | Comando | Explicação |
|------|---------|------------|
| Abrir Menu de Completação | Ctrl + Espaço | Mostra sugestões de completação |
| Selecionar Completação | Enter | Confirma a sugestão selecionada |
| Próxima Posição do Snippet | Tab | Move para o próximo campo do snippet |
| Posição Anterior do Snippet | Shift + Tab | Volta para o campo anterior do snippet |
| Próxima Completação | Seta Baixo/Ctrl + n/Ctrl + j/Tab | Navega para a próxima sugestão |
| Completação Anterior | Seta Cima/Ctrl + p/Ctrl + k/Shift + Tab | Volta para a sugestão anterior |
| Cancelar Completação | Ctrl + e | Fecha o menu de completação |

## Comandos LSP (Language Server Protocol)
| Ação                         | Comando            | Explicação                                    |
| ---------------------------- | ------------------ | --------------------------------------------- |
| Informações LSP              | Leader + li        | Mostra informações sobre o servidor LSP atual |
| Documentação ao Passar Mouse | K                  | Mostra documentação do item sob o cursor      |
| Formatar Documento           | Leader + lf        | Formata o documento atual                     |
| Diagnósticos da Linha        | gl ou Leader + ld  | Mostra diagnósticos da linha atual            |
| Ações de Código              | gra ou Leader + la | Mostra ações de código disponíveis            |
| Renomear Símbolo             | grn ou Leader + lr | Renomeia o símbolo sob o cursor               |
| Ir para Definição            | gd                 | Vai para a definição do símbolo               |
| Ir para Implementação        | gI                 | Vai para a implementação do símbolo           |

## Neo-Tree (Gerenciador de Arquivos)
| Ação | Comando | Explicação |
|------|---------|------------|
| Alternar Neo-tree | Leader + e | Abre/fecha o explorador de arquivos |
| Focar Neo-tree | Leader + o | Foca no explorador de arquivos |

## Terminal
| Ação | Comando | Explicação |
|------|---------|------------|
| Terminal Flutuante | Leader + tf | Abre um terminal em janela flutuante |
| Terminal Horizontal | Leader + th ou F7 | Abre terminal em divisão horizontal |
| Terminal Vertical | Leader + tv | Abre terminal em divisão vertical |
| Abrir Lazygit | Leader + tl | Abre interface do Lazygit |
