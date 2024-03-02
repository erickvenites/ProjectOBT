const job = [];

function listVacancy() {
  const vacancyText = job.reduce(function (textEnd, vacancy, index) {
    //1.nome,quantidade de candidatos
    textEnd += index + ". ";
    textEnd += vacancy.vacancyName;
    textEnd += "(" + vacancy.candidates.length + "candidatos)\n";
    return textEnd;
  }, "");
  alert(vacancyText);
}

function newVacancy() {
  const vacancyName = prompt("Qual nome da vaga?");
  const description = prompt("Qual a descrição da vaga?");
  const deadline = prompt("Qual a data limite da vaga?");

  const confirmation = confirm(
    "Verifique se as informações prestadas abaixo estão corretas:\n\n" +
      "vaga para: " +
      vacancyName +
      "\nDescrição: " +
      description +
      "\nData limite: " +
      deadline
  );

  if (confirmation) {
    const newVacancy = {
      vacancyName,
      description,
      deadline,
      candidates: [],
    };
    job.push(newVacancy);
    alert("Vaga criada com sucesso");
  }
}

function displayVacancy() {
  const index = prompt("Informe o indice da vaga: ");
  const vacancy = job[index];
  if (index >= job.length || index < 0) {
    alert("indice invalido");
    return;
  }
  const candidatesText = vacancy.candidates.reduce(function (
    textEnd,
    candidate
  ) {
    return textEnd + "\n - " + candidate;
  },
  "");
  alert(
    "Vaga n° " +
      index +
      "\nNome: " +
      vacancy.vacancyName +
      "\n Descrição" +
      vacancy.description +
      "\nData limite: " +
      vacancy.deadline +
      "\nQuantidade de candidatos: " +
      vacancy.candidates.length +
      "\nCandidatos Inscritos: " +
      candidatesText
  );
}

function registrations() {
  const candidate = prompt("Qual seu nome?");
  const index = prompt("Qual o indice da vaga? ");
  const vacancy = job[index];

  if (index >= job.length || index < 0) {
    alert("indice invalido");
    return;
  }

  const confirmation = confirm(
    "Verifique se as informações prestadas abaixo estão corretas:\n\n" +
      "\nNome: " +
      vacancy.vacancyName +
      "\n Descrição" +
      vacancy.description +
      "\nData limite: " +
      vacancy.deadline +
      "Nome do candidato: " +
      candidate +
      "\nIndice da vaga: " +
      index
  );
  if (confirmation) {
    vacancy.candidates.push(candidate);
    alert("Candidato Registrado com sucesso!");
  }
}
function deleteVacancy() {
  const index = prompt("Informe o indice da vaga que desaja excluir: ");
  const vacancy = job[index];

  if (index >= job.length || index < 0) {
    alert("indice invalido");
    return;
  }

  const confirmation = confirm(
    "Tem certeza que deseja excluir a vaga " +
      index +
      "?\n" +
      "\nNome: " +
      vacancy.vacancyName +
      "\n Descrição" +
      vacancy.description +
      "\nData limite: " +
      vacancy.deadline
  );
  if (confirmation) {
    job.splice(index, 1);
    alert("Vaga excluida");
  }
}

function menu() {
  const option = prompt(
    "Bem vindo ao vagas de empregos\n" +
      "Numero de vagas registradas: " +
      job.length +
      "\n\n Escolha uma ação:\n " +
      "1.Listar vagas disponiveis\n" +
      "2.Criar uma nova vaga\n" +
      "3.Visualizar candidatos nas vagas\n" +
      "4.Inscrever um candidato\n" +
      "5.Excluir uma vaga\n" +
      "6.Sair"
  );
  return option;
}

function execute() {
  let option = "";

  do {
    option = menu();

    switch (option) {
      case "1":
        listVacancy();
        break;
      case "2":
        newVacancy();
        break;
      case "3":
        displayVacancy();
        break;
      case "4":
        registrations();
        break;
      case "5":
        deleteVacancy();
        break;
      case "6":
        alert("fechando o Programa...");
        break;
      default:
        alert("Opção invalida...");
        break;
    }
  } while (option !== "6");
}

execute();
