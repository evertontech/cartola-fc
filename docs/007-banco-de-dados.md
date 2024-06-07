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
  time_id integer
}

Ref: time.tecnico_id < tecnico.id

Ref: jogador.time_id < time.id
