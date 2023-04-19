# teste-backend-nodejs-pleno

Este é um teste de construção de uma API básica com uma simples integração ao mundo externo. Utilize sua criatividade e habilidade para fazer da melhor forma que você considerar.

### Requisitos

	•	Usar o Node.js 18
	•	Usar banco de dados relacional MySQL, Postgres ou SQLite
	•	Versionar tudo em um repositório Git e adicionar um README com instruções de como fazer o deploy do seu projeto
	•	Usar padrões de projeto, SOLID, TDD e outros paradigmas modernos serão bem vistos
  
### Solução

1 - Com base no descritivo de modelo de dados abaixo, crie um banco de dados relacional contendo as tabelas, chaves e definições necessárias:
Modelo Pessoa

	•	id - inteiro, autoincremento e chave primária
  	•	nome - texto limitado a 255 caracteres e obrigatório
	•	nome_mae - texto limitado a 255 caracteres e obrigatório
  	•	nome_pai - texto limitado a 255 caracteres e opcional
  	•	cep - texto limitado a 8 caracteres e obrigatório
    	•	data_nascimento - data e obrigatória
	•	data_cadastro - data e obrigatória
  	•	data_edicao - data e obrigatória
	•	Modelo Anotação
	•	id - inteiro, autoincremento e chave primária
	•	id_pessoa - inteiro, chave estrangeira é obrigatória
  	•	titulo - texto limitado a 255 caracteres e obrigatório
	•	descricao - texto limitado a 2000 caracteres e opcional
	•	data_cadastro - data e obrigatória
	•	data_edicao - data e obrigatória
  
2 - Crie os endpoints para operações de CRUD para cada modelo considerando:

	•	Os campos data_cadastro e data_edicao devem ser preenchidos automaticamente, sem possibilidade do usuário enviar esses dados no payload do 		   endpoint.
	•	Os campos data_cadastro devem ser preenchidos automaticamente no insert e não podem mais ser alterados.
	•	Os campos data_edicao devem ser preenchidos automaticamente em cada update.
	•	O campo CEP, ao ser persistido no insert ou update, deve ser consultado em uma API externa para ser validado. Caso o CEP não seja válido 		 (não localizados dados na API externa), o resultado dos endpoints de Insert ou Update devem apontar um erro no payload no campo cep e não 		   prosseguir com a operação no banco de dados. Utilize esta API para validar os CEPs: https://viacep.com.br/
	•	No endpoint de Retrieve, o modelo localizado deve ser completado com dados do endereçamento baseado no CEP persistido. Mais uma vez, 			consulte o CEP na API acima indicada e adicione um atributo no modelo nomeado de 'endereco' que deve conter a resposta da API de CEP 			consultada.
	• Sobre o status das respostas dos endpoints:
    		•	200 em caso de sucesso
		•	400 em caso de erro de validação no payload
  	  	•	404 em caso de registro não localizado
    		•	500 em caso de erro
		
	• Sobre o corpo das respostas dos endpoints:
	    	•	Insert e Update - objeto salvo
    		•	Retrieve - objeto pesquisado
	    	•	Delete - booleano simbolizando sucesso da operação
      
3 - Criar nível de proteção por token para a API, considerando:

	• As requisições devem ser feitas com um token no cabeçalho da requisição.
	• Token precisa ser validado, caso inválido a API deve retornar uma resposta com status 403
  
4 - Criar documentação do tipo openapi v3 com Swagger para os endpoints e especificações acima

5 - Criar teste automatizados para os endpoints criados

### Envio do teste
Ao finalizar, deverá ser enviado o link do repositório e do sistema em produção, no caso de ter feito o deploy, pelo seguinte formulário: https://forms.gle/Cd2dqSe5iFuVCyod7

### Avaliação
Irá ser avaliado:

+ Seu conhecimento técnico e criatividade;
+ Sua habilidade para resolver problemas de forma simples e eficiente;
+ Boas práticas de código.
---

Boa sorte!

Equipe **#roga_rocks**
