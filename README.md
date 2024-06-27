# Desafio Front Zoox

Este teste é uma oportunidade para demonstrar suas habilidades técnicas e analíticas e nos ajudará a avaliar sua adequação para a posição.

## Critérios de avaliação:
1. Simplicidade;
2. Testabilidade;
3. Responsividade.

## Bônus:
- Fácil execução é um ponto favorável;
- Uma boa documentação facilita muito.

Se tiver qualquer dúvida é só perguntar, ligar, entrar em contato. Estaremos à disposição.

## Desafio

A ideia do desafio é criar um cenário semelhante ao que você vai vivenciar no dia a dia.

Nesse projeto, você terá que fazer um modificador de CSV simplificado, **apenas usando FrontEnd**.

**Caso de uso:** Como usuário, gostaria de importar um csv e exportar somente algumas linhas e colunas do CSV.

**Caso de uso(2):** Como usuário, gostaria de ver o histórico dos meus csv's exportados.

**Layout:** Usar o protótipo - [Link Figma](https://www.figma.com/proto/Hyh57kBO3Kn6iuJ8uXoM0L/Teste-Front-v2?page-id=0%3A1&type=design&node-id=1-5825&viewport=916%2C607%2C0.5&t=iiU3l8VOo8UymPro-1&scaling=scale-down&starting-point-node-id=1%3A5825&show-proto-sidebar=1&mode=design).

## Fluxo de uso
- Usuário vai importar um arquivo CSV válido;
- Após a importação feita, as linhas e colunas do CSV devem ser exibidas em formato de tabela;
- Usuário seleciona quais colunas ele quer visualizar/incluir através do botão "Colunas". (Devem ser exibidas/exportadas somente as colunas selecionadas);
- Usuário seleciona quais linhas quer selecionar através do checkbox da primeira coluna. (Devem ser exportadas somente as linhas selecionadas, sem alteração na tabela);
- Usuário clica em exportar tabela. A exportação faz download do arquivo CSV para máquina do usuário;
- Para cada exportação é salvo um log, que é exibido na tabela da página inicial.

## Observações técnicas importantes:
- Desenvolver utilizando VueJS;
- O armazenamento das informações deve ser feita toda no frontend;
- Pode ser utilizada a biblioteca visual de sua escolha - o visual deve ser semelhante ao protótipo;
- A solução deve ser publicada no Github e deve conter um Readme com instruções para execução.
