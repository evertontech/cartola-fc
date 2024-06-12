Table tecnico {
  id integer [primary key]
  nome varchar
}

Table time {
  id integer [primary key]
  nome varchar
  tecnico_id integer
}

Table jogador {
  id integer [primary key]
  nome varchar
  preco integer
  time_id integer
  posicao_id integer
}

Table posicao {
  id integer [primary key]
  nome varchar
}

Ref: tecnico.id - time.tecnico_id
Ref: time.id < jogador.time_id
Ref: posicao.id < jogador.posicao_id
