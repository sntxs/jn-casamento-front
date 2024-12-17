<template>
  <div v-if="carregando">
    <div v-if="screenWidth >= 769" class="loading-screen">
      <img src="/src/img/icone/icone.png" alt="Logo JN" class="loading-logo">
    </div>
    <div v-else class="loading-screen">
      <h1 class="loading-logo">J & N</h1>
    </div>
  </div>
  <div v-else class="app">
    <!-- Header -->
    <nav
      :class="['navbar', 'navbar-expand-lg', 'navbar-light', 'bg-white', 'fixed-top', 'shadow-sm', { 'navbar-hidden': navbarEscondida }]">
      <div class="container">
        <a class="navbar-brand" href="#">J & N</a>

        <button class="navbar-toggler" type="button" @click="toggleMenu">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" :class="{ show: menuAberto }" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#home" @click.prevent="scrollToSection('home')">Ínicio</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#historia" @click.prevent="scrollToSection('historia')">História</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#presentes" @click.prevent="scrollToSection('presentes')">Presentes</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero d-flex align-items-center fade-in">
      <div class="container text-center">
        <h1 class="display-4">Juliana & Natã</h1>
        <p class="lead">Vamos celebrar nosso amor!</p>
        <p class="date">15.02.2025</p>
      </div>
    </section>

    <!-- Nossa História -->
    <section id="historia" class="sobre-nos py-5 bg-light">
      <div class="container">
        <h2 class="text-center mb-5">Nossa História</h2>
        <div class="row align-items-center">
          <div class="col-md-6">
            <!-- Carrossel de Imagens -->
            <div id="carouselHistoria" class="carousel slide" data-bs-ride="carousel">
              <div class="carousel-inner">
                <div class="carousel-item active">
                  <img src="/src/img/img-jn/jn1.png" alt="Juliana e Natã"
                    class="d-block w-100 img-fluid rounded shadow">
                </div>
                <div class="carousel-item">
                  <img src="/src/img/img-jn/jn2.png" alt="Juliana e Natã"
                    class="d-block w-100 img-fluid rounded shadow">
                </div>
              </div>
              <button class="carousel-control-prev" type="button" data-bs-target="#carouselHistoria"
                data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Anterior</span>
              </button>
              <button class="carousel-control-next" type="button" data-bs-target="#carouselHistoria"
                data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Próximo</span>
              </button>
            </div>
          </div>
          <div class="col-md-6">
            <div class="historia-content p-4">
              <h3 class="mb-4">Um resumo de como tudo começou</h3>
              <p>
                Em 2020, um ano tão bagunçado que até os pais da Juliana, meio sem opções, decidiram amar um cara que
                nem conheciam. Bastou o sujeito pisar na casa deles pra já pensarem: "É esse! Esse aí vai trazer paz
                pra nossa família e, de quebra, pro mundo." E assim começou uma história de amor abençoada, onde os
                planos de Deus se revelaram de forma extraordinária em nossas vidas.
              </p>
              <p>
                Em 2021, o cara, trabalhador de turno – das 13h às 22h –, nem imaginava o que vinha pela frente.
                Juliana,
                esperta como só ela, logo viu uma chance. Nos intervalos dele, lá pelas 17h, ela aparecia de surpresa.
                Não
                era porque era romântica ou porque queria fazer média... era porque o caminho até o trabalho dele
                passava
                pelo Burger King. E foi assim que o amor deles foi construído: hambúrguer por hambúrguer. Ele sempre no
                Rodeio, ela no Whopper, e a paixão indo junto com as calorias. Desde o início, ela já tinha certeza:
                "Esse é pra casar – desde que continue pagando os lanches."
              </p>
              <p>
                Aí chegou o dia, 23 de dezembro de 2021. O cara decidiu que ia pedir ela em namoro. Ou melhor, tentou
                decidir. Ensaiou tanto na frente do espelho que até o reflexo já tava cansado. Mas na hora de agir... o
                nervosismo venceu. Pediu, sim – mas pros pais dela, não pra ela! Juliana, rindo por dentro, aceitou.
                Mas, claro, só depois de deixar claro que ele continuaria bancando os combos (no caso, quem bancou por
                um bom tempo foi ela, tá?).
              </p>
              <p>
                Dois anos depois, já em 20 de dezembro de 2023, ele percebeu que era hora de subir o nível. O amor tava
                crescendo, mas a expectativa dela também. Com a ajuda da família dela e o poder do 13º, ele bolou um
                pedido de noivado todo bonitinho. Foi quase um desastre, porque Juliana é ligeira e quase estragou a
                surpresa, mas deu tudo certo no fim. Ela aceitou, já pensando no próximo passo: casamento, bolo de três
                andares e, se possível, open SESAMO (e nós teremos!).
              </p>
              <p>
                Agora, no dia 15 de fevereiro de 2025, Deus se prepara para mais uma cena épica dessa história que Ele
                mesmo escreveu. Vai
                ter casamento, vai ter emoção, e, com um pouco de sorte, vai ter hambúrguer pra fechar a noite. Afinal,
                algumas tradições são simplesmente sagradas. E o amor deles, abençoado por Deus, é eterno.
              </p>
              <div class="detalhes mt-4">
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Lista de Presentes -->
    <section id="presentes" class="presentes py-5">
      <div class="container">
        <h2 class="text-center mb-5">Presentes que podem nos dar</h2>
        
        <!-- Adicione o campo de pesquisa -->
        <div class="search-container mb-4">
          <input 
            type="text" 
            class="form-control search-input" 
            placeholder="Pesquisar presente..." 
            v-model="termoPesquisa"
          >
        </div>

        <div class="text-center mt-4">
          <button class="btn btn-secondary me-2" @click="paginaAnterior" :disabled="paginaAtual === 0">
            Anterior
          </button>
          <button class="btn btn-secondary" @click="proximaPagina" :disabled="paginaAtual >= totalPaginas - 1">
            Próxima
          </button>
        </div>
        <div class="row">
          <div v-for="(presente, index) in presentesPaginados" :key="presente.id" class="col-md-4 mt-3">
            <div class="card h-100">
              <img :src="presente.imagem" class="card-img-top" :alt="presente.nome">
              <div class="card-body">
                <h5 class="card-title">{{ presente.nome }}</h5>
                <p class="card-text">R$ {{ presente.valor }}</p>
                <button @click="abrirModalSelecaoPagamento(presente)" class="btn btn-primary"
                  :disabled="presente.comprado">
                  {{ presente.comprado ? 'Presente Reservado' : 'Presentear' }}
                </button>
              </div>
            </div>
          </div>
        </div>
        <div class="text-center mt-4">
          <button class="btn btn-secondary me-2" @click="paginaAnterior" :disabled="paginaAtual === 0">
            Anterior
          </button>
          <button class="btn btn-secondary" @click="proximaPagina" :disabled="paginaAtual >= totalPaginas - 1">
            Próxima
          </button>
        </div>
      </div>
    </section>

    <!-- Modal PIX -->
    <div class="modal fade" id="pixModal" tabindex="-1" aria-labelledby="pixModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="pixModalLabel">Pagamento via PIX</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body text-center">
            <h6>{{ presenteSelecionado?.nome }}</h6>
            <p class="text-muted">Valor: R$ {{ presenteSelecionado?.valor }}</p>

            <!-- Loading -->
            <div v-if="carregandoPix" class="text-center my-4">
              <div class="spinner-border text-primary" role="status">
                <span class="visually-hidden">Carregando...</span>
              </div>
              <p class="mt-2">Gerando QR Code...</p>
            </div>

            <!-- QR Code e Informaç��es -->
            <div v-else-if="dadosPix">
              <img :src="`data:image/png;base64,${dadosPix.qrCodeBase64}`" alt="QR Code PIX" class="img-fluid mb-3"
                style="max-width: 250px;">

              <div class="mb-3">
                <p class="mb-1">Código PIX:</p>
                <div class="input-group">
                  <input type="text" class="form-control" :value="dadosPix.qrCode" readonly>
                  <button class="btn btn-outline-primary" type="button" @click="copiarCodigo(dadosPix.qrCode)">
                    Copiar
                  </button>
                </div>
              </div>

              <div class="alert alert-info">
                <small>
                  <p class="mb-1"><strong>ID da Transação:</strong> {{ dadosPix.id }}</p>
                  <p class="mb-1"><strong>Status:</strong> {{ traduzirStatus(dadosPix.status) }}</p>
                  <p class="mb-1"><strong>Data de Criação:</strong> {{ formatarData(dadosPix.date_created) }}</p>
                  <p class="mb-0"><strong>Expira em:</strong> {{ formatarData(dadosPix.date_of_expiration) }}</p>
                </small>
              </div>

              <div class="alert alert-warning">
                <small>
                  Por favor, realize o pagamento de <strong>R$ {{ dadosPix.valor }}</strong> através do QR Code ou
                  código PIX acima.
                  O pagamento expira em 24 horas.
                </small>
              </div>
            </div>

            <!-- Erro -->
            <div v-else-if="erroPix" class="alert alert-danger">
              {{ erroPix }}
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal de Confirmação de Pagamento -->
    <div class="modal fade" id="confirmacaoPagamentoModal" tabindex="-1">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Confirmação de Pagamento</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body text-center">
            <p>Pagamento confirmado com sucesso!</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modifique o modal de confirmação para pedir o nome do doador -->
    <!-- <div class="modal fade" id="confirmacaoModal" tabindex="-1">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Nome do Doador</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body text-center">
            <input type="text" class="form-control mt-3" placeholder="Nome do doador ou casal" v-model="nomeDoador">
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancelar</button>
            <button type="button" class="btn btn-primary" @click="confirmarPagamento">Confirmar</button>
          </div>
        </div>
      </div>
    </div> -->

    <!-- Adicione um modal de agradecimento -->
    <div class="modal fade" id="agradecimentoModal" tabindex="-1">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Agradecimento</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body text-center">
            <p>{{ mensagemAgradecimento }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modifique o modal de admin -->
    <div class="modal fade" id="adminModal" tabindex="-1">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Modo Administrador</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body">
            <!-- Tela de login -->
            <div v-if="!isAdmin">
              <div class="mb-3">
                <label for="adminPassword" class="form-label">Senha de Administrador</label>
                <input type="password" class="form-control" id="adminPassword" v-model="adminPassword"
                  @keyup.enter="verificarSenha">
              </div>
              <button class="btn btn-primary" @click="verificarSenha">Entrar</button>
              <p class="text-danger mt-2" v-if="senhaErrada">Senha incorreta!</p>
            </div>

            <!-- Lista de presentes (só aparece após login) -->
            <div v-else class="list-group">
              <button v-for="presente in presentes" :key="presente.id"
                class="list-group-item list-group-item-action d-flex justify-content-between align-items-center"
                @click="resetarPresente(presente)">
                {{ presente.nome }}
                <span class="badge bg-primary" v-if="presente.comprado">Reservado por {{ presente.doador }}</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="bg-light py-4 mt-5">
      <div class="container text-center">
        <h5>Juliana & Natã</h5>
        <p class="mb-0">15.02.2025</p>
        <p class="text-muted">Com amor ❤️</p>
        <button class="btn btn-link text-muted admin-button" style="font-size: 0.8em;" @click="abrirModalAdmin">

        </button>
      </div>
    </footer>

    <!-- Adicione o modal de seleção de método de pagamento -->
    <div class="modal fade" id="selecaoPagamentoModal" tabindex="-1">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Escolha a forma de pagamento</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body">
            <h6>{{ presenteSelecionado?.nome }}</h6>
            <p class="text-muted">Valor: R$ {{ presenteSelecionado?.valor }}</p>

            <div class="d-grid gap-3">
              <button class="btn btn-outline-primary" @click="selecionarMetodoPagamento('pix')">
                <i class="bi bi-qr-code"></i> Pagar com PIX
              </button>
              <button class="btn btn-outline-primary" @click="selecionarMetodoPagamento('cartao')">
                <i class="bi bi-credit-card"></i> Pagar com Cartão
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed, watch } from 'vue'
import { Modal } from 'bootstrap'

// Função para embaralhar a lista de presentes
function shuffle(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  return array;
}

const presenteSelecionado = ref(null)

const presentes = ref(shuffle([
  {
    id: 1,
    nome: 'TV 50 polegadas',
    valor: 3000,
    imagem: 'https://m.media-amazon.com/images/I/51O+lnoMUUL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 2,
    nome: 'Geladeira',
    valor: 6000,
    imagem: 'https://gazin-images.gazin.com.br/Mvn8MOx_yKllhSpto8otmYlEEks=/828x/filters:format(webp):quality(75)/https://gazin-images.gazin.com.br/z3vJ2GhmkGQNtrqGCQr_W8ZD-7o=/filters:format(webp):quality(75)/https://gazin-marketplace.s3.amazonaws.com/midias/imagens/2023/09/geladeira-refrigerador-consul-450l-frost-free-duplex-filtro-antiodor-crm56fk-132309370130.jpg',
    comprado: false
  },
  {
    id: 3,
    nome: 'Fogão Inox 4 Bocas',
    valor: 3000,
    imagem: 'https://a-static.mlcdn.com.br/1500x1500/fogao-4-bocas-electrolux-prata-efficient-perfectcook-fe4is/magazineluiza/237654700/0c6fe25b4c2272e0310335d5d97bcba1.jpg',
    comprado: false
  },
  {
    id: 4,
    nome: 'Ar Condicionado 9000 BTUs',
    valor: 2000,
    imagem: 'https://encrypted-tbn1.gstatic.com/shopping?q=tbn:ANd9GcSLJgsa96Jc4WmRdXB1_ZRM_ZTj72yP-RJPwl6099oCPpgtBSrKrv3vbHEyjh9b9FIDy-yWrxq8wyKHGPtOQkfinG3Qd4uFK4xCxAwpkk6L&usqp=CAE',
    comprado: false
  },
  {
    id: 5,
    nome: 'Ar Condicionado 12000 BTUs',
    valor: 2100,
    imagem: 'https://m.media-amazon.com/images/I/51Ap48E9JDL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 6,
    nome: 'Colchão Box Casal King Size',
    valor: 5000,
    imagem: 'https://imgs.casasbahia.com.br/55060577/1g.jpg',
    comprado: false
  },
  {
    id: 7,
    nome: 'Sofá Retrátil 3 Lugares Bege',
    valor: 3500,
    imagem: 'https://static.mobly.com.br/r/2000x2000/p/Mobly-SofC3A1-3-Lugares-RetrC3A1til-e-ReclinC3A1vel-Lupin-Velosuede-Bege-7102-0491811-1.jpg?_gl=1*wh3019*_gcl_aw*R0NMLjE3MzQ0NDgzMTAuQ2p3S0NBaUEzNFM3QmhBdEVpd0FDWnp2NFZrSDgyNXJHRDJBS19qaUs4TVk5NmhSY0dVaVp1UE1yd3Q0RGV4NnAtQ3k3WjFnZkY1c1F4b0NfZjBRQXZEX0J3RQ..*_ga*MTg4NjE0MTkzMi4xNzM0NDQ4MzEw*_ga_52S02DHY6L*MTczNDQ0ODMxMC4xLjAuMTczNDQ0ODMxMS41OS4wLjA.',
    comprado: false
  },
  {
    id: 8,
    nome: 'Painel de TV Branco com Madeira Clara',
    valor: 1700,
    imagem: 'https://static.mobly.com.br/r/2000x2000/p/Modern-Painel-para-TV-atC3A9-60-Polegadas-Roma-Branco-e-Cedro-6709-5708521-1.jpg?_gl=1*1y2kpgz*_gcl_aw*R0NMLjE3MzQ0NDgzMzguQ2p3S0NBaUEzNFM3QmhBdEVpd0FDWnp2NFZrSDgyNXJHRDJBS19qaUs4TVk5NmhSY0dVaVp1UE1yd3Q0RGV4NnAtQ3k3WjFnZkY1c1F4b0NfZjBRQXZEX0J3RQ..*_gcl_au*MTMwNjI0ODMxMy4xNzM0NDQ4MzEy*_ga*MTg4NjE0MTkzMi4xNzM0NDQ4MzEw*_ga_52S02DHY6L*MTczNDQ0ODMxMC4xLjEuMTczNDQ0ODQwMS41OS4wLjA.',
    comprado: false
  },
  {
    id: 9,
    nome: 'Batedeira',
    valor: 600,
    imagem: 'https://a-static.mlcdn.com.br/1500x1500/batedeira-planetaria-mondial-preto-e-inox-700w-premium-12-velocidades/magazineluiza/021259300/69394484e36b1df50d18ce8ee8deac76.jpg',
    comprado: false
  },
  {
    id: 10,
    nome: 'Liquidificador',
    valor: 400,
    imagem: 'https://noivos.casar.com/img/presentes/shopping-camicado/Liquidificador_Super_Chef.jpg',
    comprado: false
  },
  {
    id: 11,
    nome: 'Mixer',
    valor: 400,
    imagem: 'https://m.media-amazon.com/images/I/51pdYg3ULPL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 12,
    nome: 'Jogo de Panelas',
    valor: 800,
    imagem: 'https://m.media-amazon.com/images/I/61AjgTFEaRL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 13,
    nome: 'Panela de Pressão',
    valor: 450,
    imagem: 'https://a-static.mlcdn.com.br/1500x1500/panela-de-pressao-fast-cereja-antiaderente-bege-fechamento-externo-cozimento-rapido-aluminio-nacional-45-litros/nacionalutilidadesdomesticas/15960713011/d0a1797040f06e78eaacc644f1cdd84b.jpeg',
    comprado: false
  },
  {
    id: 14,
    nome: 'Panela de Arroz Elétrica',
    valor: 600,
    imagem: 'https://imgs.casasbahia.com.br/55066647/1g.jpg',
    comprado: false
  },
  {
    id: 15,
    nome: 'Faqueiro Completo',
    valor: 420,
    imagem: 'https://m.media-amazon.com/images/I/61viHSB7i4L._AC_SX679_.jpg',
    comprado: false
  },
  {
    id: 16,
    nome: 'Conjunto de Pratos e Talheres',
    valor: 510,
    imagem: 'https://encrypted-tbn3.gstatic.com/shopping?q=tbn:ANd9GcTtnq5GQeXBAK9kEV1SyoddhMYgPeAagNS_YZkS4W9CQg-c0ThT6USRD2N_BqjAycuPKaXHDwiYYy3m9MZ8k1X4WWIbiXXve1Wm5CLOXqI0qGT6Uyq3NaIx&usqp=CAE',
    comprado: false
  },
  {
    id: 17,
    nome: 'Jogo de Copos Completo',
    valor: 300,
    imagem: 'https://imgs.extra.com.br/1563534874/1xg.jpg',
    comprado: false
  },
  {
    id: 18,
    nome: 'Cafeteira',
    valor: 500,
    imagem: 'https://m.media-amazon.com/images/I/51rsO-NkHVL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 19,
    nome: 'Torradeira',
    valor: 360,
    imagem: 'https://m.media-amazon.com/images/I/51pcpIXaj0L._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 20,
    nome: 'Air Fryer',
    valor: 500,
    imagem: 'https://m.media-amazon.com/images/I/81DHdkzgECL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 21,
    nome: 'Kit Potes Herméticos',
    valor: 300,
    imagem: 'https://encrypted-tbn2.gstatic.com/shopping?q=tbn:ANd9GcRu-mwp2B0r1zyZmvSeix5igQmVyYRzZCg-kBelJtx1gUEq-wgvrL_N4TMDT-ZkgbUulwGo115hFpzVSz0eE9tP8RNcoBIQ2kiz7foy26fGnOsGwZwemm_Qaxhoy_6ltg&usqp=CAc',
    comprado: false
  },
  {
    id: 22,
    nome: 'Aparelho de Jantar Formal',
    valor: 900,
    imagem: 'https://m.media-amazon.com/images/I/81m1ryjy2xL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 23,
    nome: 'Kit Sousplat e Jogos Americanos',
    valor: 199,
    imagem: 'https://m.media-amazon.com/images/I/716vXxvmvkL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 24,
    nome: 'Jogo de Taças',
    valor: 199,
    imagem: 'https://m.media-amazon.com/images/I/51CCynfziUL._AC_SL1300_.jpg',
    comprado: false
  },
  {
    id: 25,
    nome: 'Jogo de Travessas',
    valor: 299,
    imagem: 'https://m.media-amazon.com/images/I/51wQ2UujUnL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 26,
    nome: 'Kit Almofadas Decorativas',
    valor: 99,
    imagem: 'https://m.media-amazon.com/images/I/81T4JwSX8zL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 27,
    nome: 'Kit Mantas para Sofá',
    valor: 199,
    imagem: 'https://m.media-amazon.com/images/I/71ArJQncJfL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 28,
    nome: 'Jogo de Cama Completo',
    valor: 499,
    imagem: 'https://m.media-amazon.com/images/I/31TgkyHJ3aL._AC_.jpg',
    comprado: false
  },
  {
    id: 29,
    nome: 'Kit Travesseiros',
    valor: 269,
    imagem: 'https://m.media-amazon.com/images/I/51g1PznpAdL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 30,
    nome: 'Kit Roupões de Banho',
    valor: 399,
    imagem: 'https://down-br.img.susercontent.com/file/br-11134207-7r98o-ly8loqdupkt18e.webp',
    comprado: false
  },
  {
    id: 31,
    nome: 'Jogo de Toalhas Completo',
    valor: 299,
    imagem: 'https://m.media-amazon.com/images/I/71oAKOMXPHL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 32,
    nome: 'Kit Tapetes para Banheiro',
    valor: 99,
    imagem: 'https://m.media-amazon.com/images/I/61tCtMvwf5L._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 33,
    nome: 'Cesto de Roupas',
    valor: 290,
    imagem: 'https://m.media-amazon.com/images/I/61Ku1AabY7L._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 34,
    nome: 'Tábua de Passar',
    valor: 249,
    imagem: 'https://m.media-amazon.com/images/I/51fe6AxBPkL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 35,
    nome: 'Ferro de Passar Roupa',
    valor: 380,
    imagem: 'https://m.media-amazon.com/images/I/61G0nm+-tuL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 36,
    nome: 'Aspirador de Pó',
    valor: 399,
    imagem: 'https://m.media-amazon.com/images/I/71zOYFOSMqL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 37,
    nome: 'Ventilador de Teto',
    valor: 650,
    imagem: 'https://m.media-amazon.com/images/I/41mDrX7RDOL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 39,
    nome: 'Kit Malas de Viagem',
    valor: 899,
    imagem: 'https://m.media-amazon.com/images/I/51uIj-rr4tL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 40,
    nome: 'Kit Utensílios para Churrasco',
    valor: 399,
    imagem: 'https://m.media-amazon.com/images/I/61TqSpedRgL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 41,
    nome: 'Caixa de Ferramentas',
    valor: 500,
    imagem: 'https://m.media-amazon.com/images/I/81NzamswRGL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 42,
    nome: 'Kit Vasos Decorativos',
    valor: 199,
    imagem: 'https://m.media-amazon.com/images/I/51x2HiSuBfL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 43,
    nome: 'Micro-ondas',
    valor: 799,
    imagem: 'https://m.media-amazon.com/images/I/41AwRmHGdgL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 44,
    nome: 'Máquina Lava e Seca',
    valor: 5300,
    imagem: 'https://m.media-amazon.com/images/I/51c2OEek8yL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 46,
    nome: 'Lava-louças',
    valor: 3999,
    imagem: 'https://m.media-amazon.com/images/I/41nJML+uGVL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 47,
    nome: 'Poltrona Decorativa',
    valor: 599,
    imagem: 'https://m.media-amazon.com/images/I/51jB6JHIdLL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 48,
    nome: 'Mesa de Centro',
    valor: 499,
    imagem: 'https://m.media-amazon.com/images/I/61g5rHAHkJL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 49,
    nome: 'Mesa de Jantar com Cadeiras',
    valor: 2499,
    imagem: 'https://m.media-amazon.com/images/I/71la68P82wL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 50,
    nome: 'Aparador de jantar',
    valor: 1999,
    imagem: 'https://m.media-amazon.com/images/I/61Lkx54nzlL._AC_SL1280_.jpg',
    comprado: false
  },
  {
    id: 51,
    nome: 'Cristaleira',
    valor: 1699,
    imagem: 'https://m.media-amazon.com/images/I/41QJK-HZ-AL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 52,
    nome: 'Guarda-roupa',
    valor: 3699,
    imagem: 'https://m.media-amazon.com/images/I/7166gHd7UlL._AC_SL1500_.jpg',
    comprado: false
  },
  {
    id: 53,
    nome: 'Kit Criados-mudos',
    valor: 699,
    imagem: 'https://m.media-amazon.com/images/I/61qnNqfN4dL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 54,
    nome: 'Cômoda',
    valor: 1499,
    imagem: 'https://m.media-amazon.com/images/I/51GAZoIlPBL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 55,
    nome: 'Kit Armários Modulados',
    valor: 3000,
    imagem: 'https://m.media-amazon.com/images/I/51wyofG5Z-L._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 56,
    nome: 'Espelho com Armário',
    valor: 699,
    imagem: 'https://m.media-amazon.com/images/I/61lKu9lwRoL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 57,
    nome: 'Armário Multiuso',
    valor: 1890,
    imagem: 'https://m.media-amazon.com/images/I/41yO6wzapWL._AC_SL1024_.jpg',
    comprado: false
  },
  {
    id: 58,
    nome: 'Kit Estantes',
    valor: 899,
    imagem: 'https://m.media-amazon.com/images/I/71ydkq07auL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 59,
    nome: 'Mesa e Cadeiras de Varanda',
    valor: 1299,
    imagem: 'https://m.media-amazon.com/images/I/617Ucgtk4rL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 61,
    nome: 'Churrasqueira a Carvão',
    valor: 899,
    imagem: 'https://m.media-amazon.com/images/I/61TGo6xPLdL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 62,
    nome: 'Guarda-roupas Quarto Extra',
    valor: 2600,
    imagem: 'https://m.media-amazon.com/images/I/713lKjBC8UL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 63,
    nome: 'Escrivaninha Home Office',
    valor: 799,
    imagem: 'https://m.media-amazon.com/images/I/71vJtkqhn+L._AC_SY300_SX300_.jpg',
    comprado: false
  },
  {
    id: 64,
    nome: 'Ventilador',
    valor: 499,
    imagem: 'https://m.media-amazon.com/images/I/51rACDpWe8L._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 65,
    nome: 'Kit Porta Temperos',
    valor: 390,
    imagem: 'https://m.media-amazon.com/images/I/61OG7XRQh5L._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 66,
    nome: 'Kit Porta Copos',
    valor: 149,
    imagem: 'https://m.media-amazon.com/images/I/61O60QJbRzL._AC_.jpg',
    comprado: false
  },
  {
    id: 67,
    nome: 'Kit Porta Guardanapos',
    valor: 79,
    imagem: 'https://m.media-amazon.com/images/I/61Kvtw5oOkS._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 68,
    nome: 'Jogo de Tigelas',
    valor: 199,
    imagem: 'https://m.media-amazon.com/images/I/51hoeyPpjuL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 69,
    nome: 'Fritadeira a Ar',
    valor: 699,
    imagem: 'https://m.media-amazon.com/images/I/51wwp25UBVL._AC_SL1000_.jpg',
    comprado: false
  },
  {
    id: 70,
    nome: 'Kit Prateleiras',
    valor: 699,
    imagem: 'https://m.media-amazon.com/images/I/61M1M2ChwnL._AC_SL1200_.jpg',
    comprado: false
  },
  {
    id: 71,
    nome: 'Cadeira Escritório',
    valor: 1400,
    imagem: 'https://m.media-amazon.com/images/I/41I3Eaax9aL._AC_.jpg',
    comprado: false
  },
  {
    id: 72,
    nome: 'Celular novo',
    valor: 4000,
    imagem: 'https://www.amazon.com.br/Smartphone-Samsung-Galaxy-256GB-Infinita/dp/B0CBCP5ZWC/ref=sr_1_7?__mk_pt_BR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3K6QHNT2JNVKT&dib=eyJ2IjoiMSJ9.VXxD3euS8enk52qej8_FDam7TwWHZywOv0vIncIyfbxLCJn5UfwRXlvNklZZWipmggjE1t87RsPUwKUTPS4_U3TNexv5RTERyJ0eZdJ8YVQM6_UWA-pHFqTBBXu-sKcGthcnuqCSn6OkEsihxtfsrHJIfsSj0w0-RTlj1cOc_nzx-KkGNOK85q173T3ivaTvnwi_OvwvmeZqaQP67-Xx6giRion8YqXSqdTVaaxdHByUj-lnKJET50F0acYitYHqR0VRctnIjvyDbkWxjmqjaVlnXGahT_NNQ0PyrBLUG5I.F4TAC1R94bRE9Iu1hRfjwTjV9qsf1jRiTBrSfUBjO-o&dib_tag=se&keywords=galaxy+s23&qid=1734453624&sprefix=galaxy+s2%2Caps%2C258&sr=8-7',
    comprado: false
  },
]))

localStorage.setItem('presentes', JSON.stringify(presentes.value))

const dadosPix = ref(null)
const carregandoPix = ref(false)
const erroPix = ref(null)

const metodoPagamento = ref('')

const selecionarMetodoPagamento = async (metodo) => {
  // Fecha o modal de seleção
  const modalSelecao = Modal.getInstance(document.getElementById('selecaoPagamentoModal'))
  modalSelecao.hide()

  if (metodo === 'pix') {
    await mostrarPix(presenteSelecionado.value)
  } else if (metodo === 'cartao') {
    await processarPagamentoCartao(presenteSelecionado.value)
  }
}

const processarPagamentoCartao = async (presente) => {
  try {
    carregandoPix.value = true
    erroPix.value = null

    const response = await fetch('https://jn-casamento-back.vercel.app/gerar-pagamento-cartao', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        valor: presente.valor,
        descricao: `Presente: ${presente.nome}`
      })
    })

    const data = await response.json()
    if (!response.ok) throw new Error(data.error || 'Erro ao gerar pagamento')

    // Abre a página de pagamento do Mercado Pago em uma nova aba
    window.open(data.init_point, '_blank')

    // Abre o modal de confirmação após redirecionar
    /* setTimeout(() => {
      abrirModalConfirmacao()
    }, 1000) */
  } catch (error) {
    console.error('Erro ao processar pagamento:', error)
    alert('Erro ao processar pagamento. Por favor, tente novamente.')
  } finally {
    carregandoPix.value = false
  }
}

const mostrarPix = async (presente) => {
  try {
    carregandoPix.value = true;
    erroPix.value = null;
    dadosPix.value = null;

    const response = await fetch('https://jn-casamento-back.vercel.app/gerar-pix', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        valor: presente.valor,
        descricao: `Presente: ${presente.nome}`
      })
    });

    const data = await response.json();
    if (!response.ok) throw new Error(data.error || 'Erro ao gerar PIX');

    dadosPix.value = data;
    const modal = new Modal(document.getElementById('pixModal'));
    modal.show();
  } catch (error) {
    console.error('Erro ao gerar PIX:', error);
    erroPix.value = 'Erro ao gerar o QR Code PIX. Por favor, tente novamente.';
  } finally {
    carregandoPix.value = false;
  }
};

const copiarCodigo = async (codigo) => {
  try {
    await navigator.clipboard.writeText(codigo)
    alert('Código PIX copiado!')
  } catch (err) {
    console.error('Erro ao copiar:', err)
    alert('Erro ao copiar o código')
  }
}

const traduzirStatus = (status) => {
  const statusMap = {
    pending: 'Pendente',
    approved: 'Aprovado',
    cancelled: 'Cancelado',
    rejected: 'Rejeitado'
  }
  return statusMap[status] || status
}

const formatarData = (dataString) => {
  if (!dataString) return ''
  const data = new Date(dataString)
  return data.toLocaleString('pt-BR', {
    day: '2-digit',
    month: '2-digit',
    year: 'numeric',
    hour: '2-digit',
    minute: '2-digit'
  })
}

const nomeDoador = ref('')
const mensagemAgradecimento = ref('')

/*const abrirModalConfirmacao = () => {
  const modalPix = Modal.getInstance(document.getElementById('pixModal'))
  modalPix.hide()

  const modalConfirmacao = new Modal(document.getElementById('confirmacaoModal'))
  modalConfirmacao.show()
}*/

const confirmarPagamento = () => {
  if (presenteSelecionado.value && nomeDoador.value) {
    presenteSelecionado.value.comprado = true
    presenteSelecionado.value.doador = nomeDoador.value
    localStorage.setItem('presentes', JSON.stringify(presentes.value))

    // Fecha o modal de confirmação
    //const modalConfirmacao = Modal.getInstance(document.getElementById('confirmacaoModal'))
    //modalConfirmacao.hide()

    // Define a mensagem de agradecimento
    mensagemAgradecimento.value = `Obrigado, ${nomeDoador.value}, pelo presente!`

    // Mostra o modal de agradecimento
    const modalAgradecimento = new Modal(document.getElementById('agradecimentoModal'))
    modalAgradecimento.show()

    // Fecha o modal de agradecimento após 3 segundos
    setTimeout(() => {
      modalAgradecimento.hide()
      mensagemAgradecimento.value = ''
    }, 3000)

    // Limpa o nome do doador
    nomeDoador.value = ''
  } else {
    alert('Por favor, insira o nome do doador.')
  }
}

const isAdmin = ref(false)
const adminPassword = ref('')
const senhaErrada = ref(false)
const SENHA_ADMIN = '66908540N4t4n201223'

const verificarSenha = () => {
  if (adminPassword.value === SENHA_ADMIN) {
    isAdmin.value = true
    senhaErrada.value = false
    adminPassword.value = '' // limpa a senha
  } else {
    senhaErrada.value = true
    isAdmin.value = false
  }
}

const resetarPresente = (presente) => {
  if (!isAdmin.value) return

  if (confirm(`Deseja realmente liberar o presente "${presente.nome}"?`)) {
    presente.comprado = false
    presente.doador = null
    localStorage.setItem('presentes', JSON.stringify(presentes.value))
    alert('Presente liberado com sucesso!')
  }
}

const abrirModalAdmin = () => {
  isAdmin.value = false // reseta o estado de admin
  senhaErrada.value = false // reseta o erro de senha
  const adminModal = new Modal(document.getElementById('adminModal'))

  // Adiciona um evento para quando o modal for fechado
  adminModal._element.addEventListener('hidden.bs.modal', () => {
    window.location.href = '#home'; // Redireciona para a seção "home"
    window.location.reload(); // Recarrega a página
  });

  adminModal.show()
}

const menuAberto = ref(false)

const toggleMenu = () => {
  menuAberto.value = !menuAberto.value
}

const navbarEscondida = ref(false)
let ultimaPosicaoScroll = 0

const handleScroll = () => {
  const posicaoAtual = window.pageYOffset
  navbarEscondida.value = posicaoAtual > ultimaPosicaoScroll
  ultimaPosicaoScroll = posicaoAtual
}

const voltarAoTopo = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const paginaAtual = ref(0)
const itensPorPagina = 9

const termoPesquisa = ref('')

const presentesPaginados = computed(() => {
  let presentesFiltrados = presentes.value
  
  if (termoPesquisa.value) {
    const termo = removerAcentos(termoPesquisa.value.toLowerCase())
    presentesFiltrados = presentes.value.filter(presente => 
      removerAcentos(presente.nome.toLowerCase()).includes(termo)
    )
  }
  
  const start = paginaAtual.value * itensPorPagina
  const end = start + itensPorPagina
  return presentesFiltrados.slice(start, end)
})

const totalPaginas = computed(() => {
  let presentesFiltrados = presentes.value
  if (termoPesquisa.value) {
    const termo = removerAcentos(termoPesquisa.value.toLowerCase())
    presentesFiltrados = presentes.value.filter(presente => 
      removerAcentos(presente.nome.toLowerCase()).includes(termo)
    )
  }
  return Math.ceil(presentesFiltrados.length / itensPorPagina)
})

const proximaPagina = () => {
  if (paginaAtual.value < totalPaginas.value - 1) {
    document.getElementById('presentes').scrollIntoView({ behavior: 'smooth' })
    paginaAtual.value++
  }
}

const paginaAnterior = () => {
  if (paginaAtual.value > 0) {
    document.getElementById('presentes').scrollIntoView({ behavior: 'smooth' })
    paginaAtual.value--
  }
}

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
};

const carregando = ref(true)
const screenWidth = ref(window.innerWidth)

const updateScreenWidth = () => {
  screenWidth.value = window.innerWidth
}

const removerAcentos = (texto) => {
  return texto.normalize('NFD').replace(/[\u0300-\u036f]/g, '')
}

watch(termoPesquisa, () => {
  paginaAtual.value = 0
})

onMounted(() => {
  window.addEventListener('resize', updateScreenWidth)
  setTimeout(() => {
    carregando.value = false
  }, 5000) // 5 segundos

  const presentesSalvos = localStorage.getItem('presentes')
  if (presentesSalvos) {
    presentes.value = JSON.parse(presentesSalvos)
  }

  // Adiciona listener para tecla secreta (Ctrl + Alt + A)
  window.addEventListener('keydown', (e) => {
    if (e.ctrlKey && e.altKey && e.key === 'a') {
      abrirModalAdmin()
    }
  })

  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateScreenWidth)
  window.removeEventListener('scroll', handleScroll)
})

const abrirModalSelecaoPagamento = (presente) => {
  presenteSelecionado.value = presente
  const modal = new Modal(document.getElementById('selecaoPagamentoModal'))
  modal.show()
}
</script>

<style>
:root {
  --primary-color: #4a90e2;
  --secondary-color: #f5f5f5;
}

body {
  font-family: 'Montserrat', sans-serif;
}

.navbar {
  transition: all 0.3s;
  font-size: 1.1rem;
  padding: 1rem 0;
}

.nav-link {
  position: relative;
  display: inline-block;
  padding: 0.5rem 1rem;
  transition: color 0.3s;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  display: block;
  margin-top: 5px;
  right: 0;
  background: var(--primary-color);
  transition: width 0.3s ease;
  -webkit-transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
  left: 0;
  background: var(--primary-color);
}

.hero {
  height: 100vh;
  background: linear-gradient(rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.8)), url('/src/img/icone/logo-jn-1.png');
  background-size: cover;
  background-position: center;
  margin-top: 56px;
}

.date {
  font-size: 2rem;
  color: #090F3B;
}

.historia-content {
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
}

html {
  scroll-behavior: smooth;
}

.navbar-hidden {
  transform: translateY(-100%);
  transition: transform 0.3s ease-in-out;
}

.btn-topo {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--primary-color);
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  z-index: 1000;
}

.logo-topo {
  width: 30px;
  height: 30px;
}

.card {
  height: 90%;
  margin: 0 20px;
  margin-bottom: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.card-img-top {
  width: 100%;
  height: 250px; 
  object-fit: contain; 
  padding: 20px; 
  background-color: #fff;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
}

.carousel-item {
  display: flex;
  justify-content: center;
  align-items: center;
}

.loading-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 2000;
}

.loading-logo {
  font-size: 3rem;
  animation: fadeInOut 5s ease-in-out forwards;
}

@keyframes fadeInOut {

  0%,
  80% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

.fade-in {
  opacity: 0;
  animation: fadeIn 2s forwards;
  animation-delay: 1s;
  /* Começa após 1 segundo */
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

.modal.fade .modal-dialog {
  transition: transform 0.3s ease-out, opacity 0.3s ease-out;
  transform: translateY(-50px);
  opacity: 0;
}

.modal.show .modal-dialog {
  transform: translateY(0);
  opacity: 1;
}

@media (max-width: 768px) {
  .loading-logo {
    font-size: 3rem;
    color: #090F3B;
  }
}

.carousel-item img {
  width: 100%;
  /* Define a largura para ocupar todo o espaço disponível */
  height: auto;
  /* Mantém a proporção da imagem */
  max-height: 650px;
  /* Define uma altura máxima para as imagens */
  object-fit: cover;
  /* Corta a imagem para preencher o espaço sem distorção */
}

.modal-body img {
  max-width: 100%;
  height: auto;
}

.alert {
  text-align: left;
}

.alert p:last-child {
  margin-bottom: 0;
}

/* Adicione estilos para os botões de seleção de pagamento */
.btn-outline-primary {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 1rem;
  font-size: 1.1rem;
}

.bi {
  font-size: 1.5rem;
}

.search-container {
  max-width: 500px;
  margin: 0 auto;
}

.search-input {
  padding: 10px 15px;
  font-size: 1.1rem;
  border-radius: 25px;
  border: 2px solid #ddd;
  transition: all 0.3s ease;
}

.search-input:focus {
  border-color: var(--primary-color);
}
</style>