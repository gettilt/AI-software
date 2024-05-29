<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Ai Software
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Artificial intelligence is going to change the way we interact with software through the use of chatbots. Existing software companies that leverage AI stand to dramatically reduce their expenses and increase their seats sold.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AAPL | Apple's Siri uses AI for voice interactions, and its focus on privacy could make its AI solutions attractive for certain applications. | chat_gpt,twitter |
| ADBE | Adobe integrates AI in its creative and marketing software, enhancing productivity and creativity through AI-driven tools. | chat_gpt,claude,twitter |
| AMZN | Amazon leverages AI across its businesses, including AWS for AI services and Alexa for voice interactions. | chat_gpt,claude,twitter,google |
| CRM | Salesforce uses AI to enhance customer relationship management, including AI chatbots for service and sales. | chat_gpt,claude |
| GOOGL | Google's extensive AI research and applications, including chatbots in its services, positions it to benefit significantly. | chat_gpt,claude,twitter,google |
| MSFT | Microsoft is heavily investing in AI for cloud computing services and Office productivity tools, which includes AI-driven chatbots. | chat_gpt,claude,twitter,google |
| NVDA | NVIDIA's GPUs are crucial for AI training and inference, directly benefiting from the increased use of AI in software. | chat_gpt,claude,twitter,google |
| SHOP | Shopify employs AI to optimize e-commerce, from personalized shopping experiences to inventory management. | chat_gpt |
| SQ | Square uses AI for financial services, including fraud detection and personalized customer experiences. | chat_gpt |
| TEAM | Atlassian is incorporating AI into its collaboration tools to improve project management and operational efficiency. | chat_gpt,claude |
| ZM | Zoom is integrating AI to enhance video communication services, including meeting summarization and real-time transcription. | chat_gpt,claude |
| DDOG |  | claude |
| MDB |  | claude |
| PATH |  | claude |
| PLTR |  | claude,google |
| SNOW |  | claude,google |
| VEEV |  | claude |
| META |  | twitter,google |
| TSLA |  | twitter,google |
| DPZ |  | google |
| UBER |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/ai-software/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/ai-software" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
