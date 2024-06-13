![Captura de tela 2024-04-17 123206](https://github.com/DalilaDeveloperMobile/Conhecendo-Linguagem-Python/assets/29806802/83eba503-c094-4431-b85f-e7b4cc9d92de)
### Passos Iniciais Realizados Nesse Bootcamp Python AI Backend Developer. [dio_me](https://www.dio.me/)
### ✅Introdução a Banco de Dados NoSQL.

### <img src="https://gifs.eco.br/wp-content/uploads/2021/06/gifs-de-coracao-7.gif" width="30px"> Operações no MongoDB:
```javascript
use viagens;

db.createCollection("usuarios")
db.createCollection("destinos")


// Ou vc pode inserir diretamente um documento e ele já ira criar a collection
db.usuarios_novo.insertOne({});

// Inserindo o primeiro documento
db.usuarios.insertOne(
    {   
        "nome": "nome",
        "data_nascimento": "1990-10-05",
        "email": "pamela.apolinario.borges@gmail.com",
        "endereco": "Av Manoel Marques de Jesus, 380 - Vila Xavier, Araraquara/SP"
    });

db.usuarios.insertMany([
    {   
        "nome": "Pamela",
        "idade": 30,
        "email": "pamela.apolinario.borges@gmail.com",
        "endereco": "Av Manoel Marques de Jesus, 380 - Vila Xavier, Araraquara/SP"
    },
    {   
        "nome": "Pamela",
        "idade": 31,
        "email": "pamela.apolinario.borges.outra@gmail.com",
        "endereco": "Av Manoel Marques de Jesus, 380 - Vila Xavier, Araraquara/SP"
    },

]);

db.destinos.insertOne({"nome":"Praia do Rosa", "descricao":"LInda praia"})


//Inserindo mais usuarios

// Inserir documentos na coleção "usuarios"
db.usuarios.insertMany([{
    nome: "João",
    idade: 25,
    cidade: "São Paulo",
    estado: "SP",
    endereco: {
      rua: "Avenida Principal",
      numero: 123,
      cidade: "São Paulo",
      estado: "SP"
    }
  }, {
    nome: "Maria",
    idade: 30,
    cidade: "Rio de Janeiro",
    estado: "RJ",
    endereco: {
      rua: "Rua Secundária",
      numero: 456,
      cidade: "Rio de Janeiro",
      estado: "RJ"
    }
},{
    nome: "Carlos",
    idade: 20,
    cidade: "São Paulo",
    estado: "SP",
    endereco: {
      rua: "Rua Principal",
      numero: 789,
      cidade: "São Paulo",
      estado: "SP"
    }
  },{
    nome: "Ana",
    idade: 35,
    cidade: "São Paulo",
    estado: "SP",
    endereco: {
      rua: "Avenida Secundária",
      numero: 1011,
      cidade: "São Paulo",
      estado: "SP"
    }
    }
    ,  
    {
    nome: "Pedro",
    idade: 28,
    cidade: "Belo Horizonte",
    estado: "MG",
    endereco: {
      rua: "Rua Principal",
      numero: 1314,
      cidade: "Belo Horizonte",
      estado: "MG"
    }
  }]);
  

// Find
db.usuarios.find({});
db.usuarios.find({"nome": "João"});
db.usuarios.findOne({"nome": "João"});
db.usuarios.findOneAndUpdate({ nome: "João" }, { $set: { idade: 26 } });
db.usuarios.findOneAndDelete({ nome: "João" });

// Update
db.usuarios.updateOne(
  { nome: "João" },
  { $set: { idade: 26 } }
);

db.usuarios.updateMany(
  { cidade: "São Paulo" },
  { $set: { estado: "SP" } }
);
db.usuarios.replaceOne(
  { nome: "João" },
  {
    nome: "John",
    idade: 27,
    cidade: "São Paulo",
    estado: "SP",
    endereco: {
      rua: "Avenida Principal",
      numero: 123
    }
  }
);

// Update Operadores
// Usando o operador $set para definir o valor de um campo específico
db.usuarios.updateOne({ nome: "João" }, { $set: { idade: 26 } });

// Usando o operador $inc para incrementar o valor de um campo numérico
db.usuarios.updateOne({ nome: "João" }, { $inc: { idade: 1 } });

// Usando o operador $rename para renomear um campo existente
db.usuarios.updateOne({ nome: "João" }, { $rename: { "endereco.rua": "endereco.nomeRua" } });

// Usando o operador $unset para remover um campo específico de um documento
db.usuarios.updateOne({ nome: "João" }, { $unset: { endereco: "" } });

// Delete
// Usando o método deleteOne() para excluir o primeiro documento que corresponde ao filtro especificado
db.usuarios.deleteOne({ nome: "João" });

// Usando o método deleteMany() para excluir todos os documentos que correspondem ao filtro especificado
db.usuarios.deleteMany({ cidade: "São Paulo" });


// Operadores Lógicos
db.usuarios.find({ $and: [{ idade: { $gte: 18 } }, { cidade: "São Paulo" }] });

db.usuarios.find({ $or: [{ idade: { $lt: 18 } }, { cidade: "Rio de Janeiro" }] });

db.usuarios.find({ idade: { $not: { $eq: 25 } } });

// Operadores de Comparação
db.usuarios.find({ idade: { $eq: 25 } });

db.usuarios.find({ idade: { $ne: 30 } });

db.usuarios.find({ idade: { $gt: 30 } });

db.usuarios.find({ idade: { $gte: 30 } });

db.usuarios.find({ idade: { $lt: 30 } });

db.usuarios.find({ idade: { $lte: 30 } });

db.usuarios.find({ cidade: { $in: ["São Paulo", "Rio de Janeiro"] } });

db.usuarios.find({ cidade: { $nin: ["São Paulo", "Rio de Janeiro"] } });


// Projeção
db.usuarios.find({}, { nome: 1, idade: 1 })

// Ordenação
db.usuarios.find().sort({ idade: 1 })
// Limitação
db.usuarios.find().limit(10)
// Paginação
db.usuarios.find().skip(10).limit(5)
```

<h3 align="center"> Made with <img src="https://gifs.eco.br/wp-content/uploads/2021/06/gifs-de-coracao-7.gif" width="30px"> by Dalila...</h3>
<div align="center"  style="display: inline-block">
  <a href="https://www.linkedin.com/in/dalila-cust%C3%B3dio-046076181/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  <a href = "mailto:dalila.dalila70@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://instagram.com/dalila.dalila70" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a target="_blank" href="https://api.whatsapp.com/send?phone=5588997138541"><img  alt="Whatsapp" width="117px" src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white"/></a> 
</div>

