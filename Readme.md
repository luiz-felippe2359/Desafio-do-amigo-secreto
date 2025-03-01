Desafio do amigo secreto

Soluçao do desafio 

//lista
let lista = [];

//colocar o nome na lista
function adicionarAmigo() {
    let nome = document.querySelector('input').value;
    
    if (nome.trim() === '') {  
        alert('Coloque um nome');
    } else {
        lista.push(nome.trim()); 
        atualizarLista();
        limparCampo();
    }
    
    console.log(lista);
}

//limpar a caixa
function limparCampo() {
    let nomeInput = document.querySelector('input');
    nomeInput.value = '';
}

//sortear o nome
function sortearAmigo() {
    if (lista.length === 0) {
        alert('A lista está vazia! Adicione nomes antes de sortear.');
    } else {
        let indiceSorteado = Math.floor(Math.random() * lista.length);
        let nomeSorteado = lista[indiceSorteado];
        alert(`O nome sorteado foi: ${nomeSorteado}`);
    }
}

//colocar o nome da lista na tela 
function atualizarLista() {
    let ul = document.querySelector('#lista-nomes'); 
    ul.innerHTML = '';

    lista.forEach(nome => {
        let li = document.createElement('li'); 
        li.textContent = nome;
        ul.appendChild(li);
    });
}