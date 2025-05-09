# 🧪 Testes de API – Swagger Petstore com Postman

## ✅ Exercício 2 – Consultar usuário (Read)

Neste teste, um usuário é consultado de forma no Pre-request Script é configurada a variável com nome do usuário, direcionando a url em GET.

# GET
{{baseUrl}}/user/{{username}}

### 🔧 Pré-requisito (Pre-request Script)

console.log("🔄 Preparando para consultar o usuário 'silvia_qa'...");

pm.variables.set("username", "silvia_qa");

🧪 Testes
console.log("👀 Dados do usuário consultado:");
console.log(pm.response.json());

pm.test("Status code é 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verifica se o primeiro nome é Silvia", function () {
    const data = pm.response.json();
    pm.expect(data.firstName).to.eql("Silvia");
});

📸 Console Postman

![Console Create](C:\Users\Silvia Leticia\Documents\Formacao QA e Testes\petstore-crud-postman\Exercício 2 read\images\console-create.png)

---

## 📁 Arquivos incluídos
collection.json – Collection exportada do Postman

README.md – Explicação do exercício

🚀 Próximos passos
✅ Atualizar usuário
✅ Deletar usuário

Em breve esses testes estarão aqui também!