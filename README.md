# conversor.moeda.api

## 🚀 Começando

>![](https://img.shields.io/badge/license-%20Escola%20Marista%20Ir.%20Ac%C3%A1cio-black) ![](https://img.shields.io/badge/version-0.3-white)
 
 O projeto se enquadra em conversão de Moedas sobre um valor.
 
>* ``Valor`` 
 
>* ``Moeda de origem`` 
 
>* ``Moeda de destino`` 
 
>* ``Selecionar moeda`` 
 
>* ``Converter`` 
 
>* ``Resultado`` 
  
## 📋 Requisitos 
 
 * requisitos são colocar os valores e a moeda que deseja ser convertida, e uma chave de API válida da ExchangeRate-API. 
 
## 📋 Informações 
 
* caso falte alguma informação, ou conste algo de errado, sera notificado. 
 
## 📋 Foto projeto 
 
![](Captura%20de%20tela%202024-10-25%20085313.png) 
 
 
## 📋 Auxilío 
 
* Com a inserção dos valores, escolha qual moeda você deseja, em seguida, aperte em converter e logo a baixo o resultado sera apresentado. 
 
## 🔧 Funcionalidades do Java-Script 🔧

 
 * 1- Recuperação de valores de entrada: A função captura os valores inseridos pelo usuário nos campos do formulário. 

 * 2- Consulta à API: Faz uma requisição à API ExchangeRate-API para obter a taxa de câmbio em tempo real.

 * 3- Conversão de moeda: A função converte o valor inserido para a moeda de destino usando a taxa de câmbio fornecida pela API.

 * 4- Exibição do resultado: O valor convertido é mostrado ao usuário no formato adequado.


# 🖇️ Partes do Código
 
~~~ JavaScript

async function getExchangeRate(daMoeda, paraMoeda){
  
    try{

        const response = await fetch(`${apiURL}${daMoeda}`);
const data = response.json();

if(data.result === "success"){
    returndata.conversion_rates[paraMoeda];
    
} else {
    throw new Error ( 'Erro ao buscar taxa de cambio');
}
    }catch (error){
        console.error('Erro:', error);
        return null;
    }
}
// 

document.getElementById('currency-converter').addEventListener ('submit', async function(event){
 
    event.preventDefault();

    //OBTER VALORES DE ENTRADA

    const valor = parseFloat(document.getElementById('amont').value);
    const daMoeda = document.getElementById(daMoeda).value;
    const paraMoeda = document.getElementById('paraMoeda').value;

    const exchangerate = await getExchangeRate (daMoeda, paraMoeda);

    if(exchangerate){

        const convertedValue = valor * exchangerate;

        console.log(convertedValue);

// console.log(convertvalue);

const conversao = document.getElementById('conversao')
conversao.textContent = `resultado: ${convertedValue.toFixed(2)}${paraMoeda};`

     } else{ 

        alert('erro ao buscar a cotacao. tente novamente');
    
}

});
   

~~~
 
 # resumo do codigo 📋

* 🖇️ 1- Verificar validade das informações
A função getExchangeRate verifica se a requisição à API foi bem-sucedida e se a taxa de câmbio foi obtida corretamente. Caso contrário, uma mensagem de erro será mostrada.

* 🖇️ 2- Faz a conversão de moeda
A função getExchangeRate realiza a conversão de moeda, utilizando as taxas de câmbio obtidas da API.

* 🖇️ 3- Valida os valores inseridos
Antes de realizar a conversão, o código valida os valores inseridos para garantir que são válidos.

## 📌 Explicação do Código
 

* Consulta de valores inseridos:

 ``O código analisa o valor inserido pelo usuário, a moeda (daMoeda) de origem e moeda (paraMoeda) de destino.``

* Exibição do resultado:

 ``O valor convertido é exibido para o usuário. Se ocorrer algum erro ao buscar as taxas, uma mensagem de erro será mostrada.``

* Eventos no formulário:

`` O código começa com a adição de um ouvinte de evento (addEventListener) para o formulário de conversão. Quando o usuário envia o formulário, o código impede o comportamento padrão de recarregar a página e, em vez disso, realiza a conversão de moeda.``

* Validação da API:

``A função getExchangeRate realiza a chamada à API usando o método fetch() e retorna a taxa de câmbio para a moeda de destino. Se houver algum erro (se a API não responder corretamente, por exemplo), a função retorna null e exibe uma mensagem de erro para o usuário.``

* Conversão de Moeda:

``A conversão é feita multiplicando o valor inserido pela taxa de câmbio recebida da API.``

* Taxas de Câmbio:

📌 ``Uma constante exchangeRates armazena taxas de câmbio fixas, organizadas em um objeto onde cada moeda de origem tem uma listagem de valores de conversão para as moedas de destino.``


##  Metodos e línguagens utilizadas 📋
 

✔️ Const
 
✔️ Document.getElementById
 
✔️ Tofixed
 
✔️ java-script
 
✔️ CSS3
 
✔️ HTML
 
# Explicação 📋
 
📌 Const
 
* 🖇️ cria uma variável cujo o valor é fixo, ou seja, uma constante somente leitura. Isso não significa que o valor é imutável, apenas que a variável constante não pode ser alterada ou retribuída.

📌 Document.getElementById
 
* 🖇️ Um método do objeto document que busca e retorna um elemento HTML pelo seu atributo id. É usado para acessar elementos do DOM (Document Object Model) para manipulação.

📌 java-script
 
* 🖇️ Uma linguagem de programação que permite adicionar interatividade às páginas web. É executada no navegador do cliente e pode manipular o DOM, fazer requisições assíncronas (como com fetch), e muito mais.

📌 Else

* 🖇️ o intemediario se algo nao acontecer

📌 CSS3
 
* 🖇️ O CSS3 é utilizado em praticamente todos os aspetos do design web moderno. Alguns exemplos incluem: Layouts Flexíveis e Responsivos: Utilizando flexbox e media queries do CSS3, os desenvolvedores podem criar layouts que se adaptam dinamicamente ao tamanho do ecrã do dispositivo.

📌 Html
 
* 🖇️ A linguagem de marcação padrão usada para criar e estruturar páginas web. HTML define a estrutura do conteúdo através de elementoS.
 

# ⚙️ Executando os códigos
 
Entre na tela de formulario, digite o campo de valor e selecione as moedas a serem convertidas e aperte em converter
 
## 📌 Foto da interface:
 
 ![](Captura%20de%20tela%202024-10-25%20085313.png)
  
## 🔩 Quais motivos do cadastro?
 
Encontrar o valor, ter uma agilidade maior para a conversao de moeda e facilitar a vida do usuario.
 
# 🛠️ Conclusão
 
>* `` Esta função de conversao de moeda é simples porem cumpre com oque promete.
 
 >* ``Ele utiliza HTML e Bootstrap para proporcionar uma interface amigável e eficaz.
 
 >* ``Ele permite que os usuários coloque os valores, as moedas e proporciona o resultado pela api.
 
 
#  📦 Tecnologias
 
## Tecnlogias utilizadas 🔧
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual_Studio_Code-0078d7?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=black)
 
 
## Fontes

- IA generativa
- GLOGLE

# Autor
 
- [Francisco Maimone](https://github.com/francisco043)
 