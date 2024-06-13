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

Table partida {
  id integer [primary key]
  data_hora datetime
  placar_casa integer
  placar_visitante integer
  casa_clube_id integer
  visitante_clube_id integer
}

Table escalacoes {
  id integer [primary key]
  usuario_id integer
  jogador_id integer
  isCapitao bool
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
  time_favorito varchar
  senha varchar
}

Ref: tecnico.id - clube.tecnico_id
Ref: clube.id < jogador.clube_id
Ref: posicao.id < jogador.posicao_id
Ref: partida.casa_clube_id - clube.id
Ref: partida.visitante_clube_id - clube.id
Ref: escalacoes.usuario_id > usuario.id
Ref: escalocoes.jogador_id > jogador.id
