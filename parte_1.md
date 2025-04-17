# Questão 1
> Explique a diferença entre os modelos de linguagem BERT e GPT. Quais são as principais características de cada um e em que cenários você recomendaria o uso de um em detrimento do outro?

R:

O GPT e o BERT se diferenciam no funcionamento.

O GPT é um modelo de geração de texto, ele opera prevendo as próximas palavras de um texto baseando-se nas anteriores, tudo isso a partir de uma lista de resultados com probabilidades entregue 
após o processamento do contexto por sua rede neural. A tendência do GPT é selecionar a próxima palavra da geração como sendo o termo de maior probabilidade, mas esse fator pode ser manipulado
pelo usuário (sob consumo de API a partir do parâmetro temperature) para que aleatoriamente seja selecionado previsões de palavras com diferentes probabilidades, ocasionando em mais variedade
e aleatoriedade na resposta.

O BERT é um modelo de compreensão de texto, que opera analisando o contexto completo. Ele realiza operações entre os tokens determinando pesos para cada. É um modelo de linguagem natural capaz de
realizar extrações de informações já vistas, sendo capaz de trazer respostas simples de classificação (boleanos, enums) sobre dados por ele processados. Além disso, ele é altamente configurável a
partir de treinamentos com presets de dados acompanhados de suas respectivas classificações.

Usos:
- Para o GPT, um uso bastante conhecido e integrado já ao cotidiano das pessoas são os chatbots para conversação. Por ser capaz de trabalhar com previsões probabilísticas, ele gera textos de forma criativa e bem estruturada. Poderoso para construir códigos, gerar frases e histórias e manter uma conversação sob uma janela de contexto.
- Para o BERT, seu destaque vai para sua poderosa capacidade de classificação. Um bom uso para ele pode ser para determinar categorias de livros em uma biblioteca virtual, filmes a partir da sipnose e até sabores de alimentos em sites de receitas.

# Questão 2
> Explique como a técnica de NER pode ser utilizada para melhorar um sistema de assistente virtual, e como você implementaria tal tecnologia (técnicas, passo a passo). Além disso, descreva os objetivos finais do produto descrito (como funciona para o usuário?).

R:

NER pode ser utilizado para adicionar mais contexto à dados categorizando-os e normalizando-os no pré-processamento, permitindo que o modelo que efetuará a análise siga um fluxo mais direto para a resposta adequada. 
Com um NER satisfatório, pode ser eliminada muita ambiguidade dos dados, o que permite com que a IA tenha uma menor tendência a compreender informações da maneira incorreta. Além disso, a classificação
dos dados via NER junto de um bom tratamento e limpeza antes da análise de IA pode aumentar exponencialmente sua eficiência de processamento economizando em ciclos de CPU.

Se eu fosse implementar NER em um sistema com algum modelo de assitente virtual, eu iria seguir as seguintes etapas:
- Captar a resposta do usuário;
- Através de um modelo de classificação pré-treinado (seja um simple model ou algo com BERT), eu enviaria o texto limpo (limetizado, sem stopwords, normalizado e tokenizado) para análise;
- Após a análise, eu poderia envolver as classificações das palavras de maior interesse (descobertas por meio de TF-IDF) em tags XML indicando o que são ou determinando que são pontos de atenção;
- Enviaria a mensagem no novo formato para o processamento do modelo do assistente virtual.
- Retornaria sua resposta ao usuário.
