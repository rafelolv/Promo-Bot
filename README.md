# Promobit Telegram Bot

Este é um bot do Telegram que envia promoções encontradas no site Promobit para um chat específico. Ele faz uso de web scraping para extrair informações sobre as promoções e as envia para o chat configurado.

## Configuração do Bot do Telegram

Para utilizar este bot, é necessário configurar um bot no Telegram e obter o token do bot e o ID do chat para onde as promoções serão enviadas. Substitua os valores das variáveis `bot_token` e `chat_id` com as suas próprias credenciais.

## Requisitos

- Python 3.7 ou superior
- Bibliotecas Python:
  - requests
  - BeautifulSoup
  - telegram
  - asyncio
  - emojis

Você pode instalar as dependências utilizando o pip:

pip install requests beautifulsoup4 python-telegram-bot asyncio emojis


## Funcionamento

O bot verifica regularmente as páginas listadas na variável `urls` em busca de novas promoções. Se uma nova promoção for encontrada, o bot a envia para o chat especificado. As promoções são verificadas a cada 2 segundos.

As promoções são extraídas da página utilizando técnicas de web scraping com BeautifulSoup. O bot verifica se houve mudanças no conteúdo das páginas para determinar se deve extrair novas promoções. Atualmente, a função `has_changes` sempre retorna True para forçar a extração de promoções em todas as iterações.

## Funcionalidades Adicionais

- O bot adiciona emojis aos títulos das promoções com base em palavras-chave. A associação entre palavras-chave e emojis está definida no dicionário `keyword_to_emoji`.
- As mensagens de promoção incluem informações sobre o preço atual, preço anterior (se disponível), URL do produto e uma imagem representativa (se disponível).

## Observações

- Este bot foi desenvolvido para fins educacionais e pode ser sujeito a alterações no site do Promobit que podem quebrar sua funcionalidade.
- O uso de web scraping pode violar os termos de serviço de alguns sites. É importante verificar os termos de serviço do site antes de usar técnicas de web scraping.

## Como Executar

1. Configure as variáveis `bot_token` e `chat_id` com as credenciais do seu bot Telegram.
2. Execute o script Python.
3. O bot começará a enviar as promoções para o chat configurado.

Certifique-se de manter o script em execução para continuar recebendo as promoções atualizadas.





## Funções Futuras

- Adicionar funcionalidade para reconhecer e processar promoções de outros sites além do Promobit e do Pelando.
- Melhorar o processo de identificação de mudanças nas páginas para evitar redundâncias.
