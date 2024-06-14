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
  clube_id integer
  posicao_id integer
  vai_jogar bool
}

Table posicao {
  id integer [primary key]
  nome varchar
}

Table estilo_defensivo {
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

Table time_usuario {
  id integer [primary key]
  usuario_id integer
  densidade integer
  linha_defensiva integer
  estilo_defensivo_id integer
  esquema_tatico_id integer
  escalacao_id integer
}

Table esquema_tatico {
  id integer [primary key]
  quantidade_zagueiros integer
  quantidade_meias integer
  quantidade_atacantes integer
}

Table escalacao {
  id integer [primary key]
  time_usuario_id integer
  jogador_id integer
  is_capitao bool
  is_titular bool
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


Ref: clube.id < jogador.clube_id
Ref: posicao.id < jogador.posicao_id
Ref: partida.casa_clube_id - clube.id
Ref: partida.visitante_clube_id - clube.id
Ref: time_usuario.usuario_id > usuario.id
Ref: time_usuario.estilo_defensivo_id > estilo_defensivo.id
Ref: time_usuario.esquema_tatico_id > esquema_tatico.id
Ref: time_usuario.escalacao_id < escalacao.id
Ref: escalacao.jogador_id > jogador.id
