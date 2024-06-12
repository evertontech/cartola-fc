Table tecnico {
  id integer [primary key]
  nome varchar
}

Table clube {
  id integer [primary key]
  nome varchar
  tecnico_id integer
}

Table jogador {
  id integer [primary key]
  nome varchar
  preco integer
  pontuacao integer
  disponivel bool
  clube_id integer
  posicao_id integer
}

Table posicao {
  id integer [primary key]
  nome varchar
}

Table confrontos {
  id integer [primary key]
  data_hora datetime
  placar_casa integer
  placar_fora integer
  casa_clube_id integer
  fora_clube_id integer
}

Table usuario {
  id integer [primary key]
  nome varchar
  cpf varchar
  data_nascimento date
  email varchar
  cep varchar
  estado varchar
  cidade varchar
  endereco varchar
  numero integer
  celular varchar
  senha varchar
}

Ref: tecnico.id - clube.tecnico_id
Ref: clube.id < jogador.clube_id
Ref: posicao.id < jogador.posicao_id
Ref: confrontos.casa_clube_id - clube.id
Ref: confrontos.fora_clube_id - clube.id
