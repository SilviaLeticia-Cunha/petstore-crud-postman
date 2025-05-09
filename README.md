# 🧪 Testes de API – Swagger Petstore com Postman

Este projeto demonstra a execução de testes de API utilizando o Postman, com base na API pública [Swagger Petstore](https://petstore.swagger.io/).

## ✅ Exercício 1 – Criar usuário (Create)

Neste teste, um usuário é criado de forma dinâmica, com `id` e `username` gerados automaticamente no Pre-request Script.

# POST
{{baseUrl}}/user

### 🔧 Pré-requisito (Pre-request Script)

let randomId = Math.floor(Math.random() * 9900) + 100;
let timestamp = new Date().getTime();
let username = `silvia_qa_${timestamp}`;

pm.environment.set("userId", randomId);
pm.environment.set("username", username);

console.log("🛠️ Executed Pre-request:");
console.log("🛠️ ID:", randomId);
console.log("🛠️ Username:", username);

📦 Body (JSON)
{
  "id": 12345,
  "username": "silvia_qa",
  "firstName": "Silvia",
  "lastName": "Leticia",
  "email": "silvia@example.com",
  "password": "senha123",
  "phone": "11999999999",
  "userStatus": 1
}

🧪 Testes
console.log("✅ User created successfully:");
console.log("Username:", pm.environment.get("username"));
console.log(pm.response.json());

pm.test("Status code é 200", function () {
    pm.response.to.have.status(200);
});

📸 Console Postman

![Console Create](console-create.png)

---

## 📁 Arquivos incluídos
collection.json – Collection exportada do Postman

README.md – Explicação do exercício

🚀 Próximos passos
✅ Consultar usuário
✅ Atualizar usuário
✅ Deletar usuário

Em breve esses testes estarão aqui também!