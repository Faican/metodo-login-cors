Aprendendo desenvolver uma API

Comando para executar cmd após montar a estrutura e testar no Code .

dotnet restore
dotnet build
dotnet run


CRIAÇÃO DO CRUD.

Instalado INSOMNIA.

Deu um pequeno erro mas corrigido com desmancando VALIDATE CERTIFICATES, é necessário no caso de estudo que não há certificações.

Get ler projetos existentes.

Post inserir novos projetos.

Put modificado os projetos.

Delete exclui o projeto 4.


CRIAR CRUD DE USUÁRIOS.

Iniciar criando as classes que faltam e fazendo/adicionando novas linhas e complementos.

Criar classe/Controllers = UsuarioController.cs
Criar classe/Models = Usuario.cs
Criar classe/Repositories = UsuarioRepository.cs
Adicionar/ExoContexts = Controllers - inserir complemento apontando para usuario "Public DbSet<Usuario>Usuarios { get, set, }
Adicionar/Program.cs = builder.Services.AddTransient<UsuarioRepository>();

Após a criação ira gerar = https://localhost:7154
Carregue a pagina e complemente = https://localhost:7154/api/usuarios
No navegador irá aparece a linha = [{"id":1,"email":"email@sp.br","senha":"1234"},{"id":2,"email":"email_dois@sp.br","senha":"1234"}]
Fazer testes do CRUD NO INSOMNIA.
Fazer testes GET/POST/PUT/DELETE.
Lembrando que o numero ou sequência de ID é automático, não sendo necessário adicionar no JASON durante a criação.

[
	{
		"id": 1,
		"email": "email@sp.br",
		"senha": "1234"
	},
	{
		"id": 2,
		"email": "email_dois@sp.br",
		"senha": "1234"
	},
	{
		"id": 5,
		"email": "email_tres@sp.br",
		"senha": "1234"
	}
]

Também é possível buscar usuário por ID= colocando o número desejado.

Criação do Token/Login/Cors

UsuárioController.cs = modificação no post/abaixo do antigo novo código.
UsuarioController.cs = adicionar authorize. // put-> /api/usuarios/{id}
        // Atualiza.

UsuarioController.cs = adicionar authorize. // delete -> /api/usuarios/{id}

Para mais informações sobre o projeto em questão acessar site com video.

https://www.youtube.com/watch?v=lIA6ltlgU8w

Insomnia - com a modificação não é possível modificar/deletar - apresenta erro 401. Funciona perfeitamente.

Teste e geração de Token = segue resultado.

{
 "email": "email_dois@sp.br",
 "senha": "1234"
}

Token gerado

{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImVtYWlsX2RvaXNAc3AuYnIiLCJqdGkiOiIyIiwiZXhwIjoxNzE3NzcwMTMzLCJpc3MiOiJleG9hcGkud2ViYXBpIiwiYXVkIjoiZXhvYXBpLndlYmFwaSJ9.RSIAC6qHlK3zYVqWhsI-FKAHImCBnlwDYnERfEg4YIc"
}

Teste feito - funcionando perfeitamente. Put/Delete = 200.




