# Desafio | Frontend

Este é um **CRUD** apenas no **lado do cliente**, ou seja, irá manter as informações armazenadas no **localStorage** do navegador.

As regras dos campos sendo utilizados são as seguintes:
* Nome: obrigatório para preenchimento
* E-mail: obrigatório para preenchimento
* Telefone: não obrigatório
* Data de nascimento: não obrigatório
* Cidade onde nasceu: não obrigatório

3 bugs foram inseridos no código. Um no HTML, um no CSS (vide o arquivo layout.jpg para referência) e um no JS (localizado na classe MyCrud).
Além disso, você deve implementar o método de remoção (localizado na classe MyCrud).

Serão avaliadas suas capacidades de leitura de código e resolução de problemas. Não se preocupe caso não consiga terminar tudo, nos envie o teste mesmo assim, destacando, logo abaixo, suas principais dificuldades e como fez para resolver os problemas.

# Resposta do participante
_Responda aqui quais foram suas dificuldades e como fez para encontrar e resolver os problemas ao enviar a solução_

# 1 - Bug no HTML:

Nossos campos obrigatórios são apenas Nome e E-mail como declarado acima.
Porém no nosso HTML cidade estava como required no nosso formulário, o que não deveria estar pois é um campo "não obrigatório".
Required é um atributo usado para indicar campos de um formulário obrigatório.

Como encontrei este bug?
Já tinha conhecimento sobre esse atributo no HTML, para ter certeza preenchi o formulário e deixei em branco o campo cidade.
Como resposta deu erro, o que não deveria acontecer pois cidade com o campo em branco deveria aceitar meu envio.

Como foi resolvido este bug?
Para resolver tirei o required no final da linha do meu código.
Assim aceitando meu envio com o campo em branco.

errado: 
name="cidade" required>

correto:
name="cidade">

# 2 - Bug no CSS:

Confome o arquivo layout.jpg para referência, o logo da contato está no centro.
O nosso logo está para esquerda, o correto seria no centro.

Como encontrei este bug?
Abri nosso arquivo usando live server, apertei f12 e dei um inspect na logo para ver os nossos styles.
Nossa logo definida como class .logo estava com text-align: left fazendo assim com que ele fique com seu posicionamento para esquerda.

Como foi resolvido este bug?
Troquei da nossa class .logo o text-align left para center.

errado:
.logo {
    padding-top: 48px;
    text-align: left;
}

correto:
.logo {
    padding-top: 48px;
    text-align: center;
}

# 3 - Bug no JS:

Quando clicamos para editar e salvar um dado inserido, estava pegando os nomes das colunas e sobrescrevendo as nossas informações.

Como encontrei este bug?
Usei console.log(map) e console.log(key) para verificar o que estava passando de informação.
O valor do for estava recebendo apenas a chave fazendo com que repetisse os dados do mesmo.
O certo seria pegar os valores das minhas chaves pelo input no edit.

Como foi resolvido este bug?
 this._table[i][key] = key; o certo seria receber o nosso parâmetro map = {} aonde pegaria os nossos valores do objeto
 junto com a key.

 Errado:
 this._table[i][key] = key;

 correto:
 this._table[i][key] = map[key]  
