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

            <!-- QR Code e Informações -->
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
import { ref, onMounted, onUnmounted, computed } from 'vue'
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
    id: 3,
    nome: 'Air Fryer',
    valor: 1,
    imagem: 'https://picsum.photos/300/200?random=3',
    comprado: false
  },
  {
    id: 4,
    nome: 'Jogo de Lençóis',
    valor: 259.90,
    imagem: 'https://picsum.photos/300/200?random=4',
    comprado: false
  },
  {
    id: 5,
    nome: 'Aspirador de Pó',
    valor: 459.90,
    imagem: 'https://picsum.photos/300/200?random=5',
    comprado: false
  },
  {
    id: 6,
    nome: 'Micro-ondas',
    valor: 599.90,
    imagem: 'https://picsum.photos/300/200?random=6',
    comprado: false
  },
  {
    id: 7,
    nome: 'Forno Elétrico',
    valor: 499.90,
    imagem: 'https://picsum.photos/300/200?random=7',
    comprado: false
  },
  {
    id: 8,
    nome: 'Máquina de Lavar',
    valor: 799.90,
    imagem: 'https://picsum.photos/300/200?random=8',
    comprado: false
  },
  {
    id: 9,
    nome: 'Secadora de Roupas',
    valor: 899.90,
    imagem: 'https://picsum.photos/300/200?random=9',
    comprado: false
  },
  {
    id: 10,
    nome: 'Fogão',
    valor: 699.90,
    imagem: 'https://picsum.photos/300/200?random=10',
    comprado: false
  },
  {
    id: 11,
    nome: 'Geladeira',
    valor: 999.90,
    imagem: 'https://picsum.photos/300/200?random=11',
    comprado: false
  },
  {
    id: 12,
    nome: 'Máquina de Café',
    valor: 399.90,
    imagem: 'https://picsum.photos/300/200?random=12',
    comprado: false
  },
  {
    id: 13,
    nome: 'Torradeira',
    valor: 149.90,
    imagem: 'https://picsum.photos/300/200?random=13',
    comprado: false
  },
  {
    id: 14,
    nome: 'Batedeira',
    valor: 249.90,
    imagem: 'https://picsum.photos/300/200?random=14',
    comprado: false
  },
  {
    id: 15,
    nome: 'Forno de Micro-ondas',
    valor: 499.90,
    imagem: 'https://picsum.photos/300/200?random=15',
    comprado: false
  },
  {
    id: 16,
    nome: 'Viagem para Noruega',
    valor: 9999.90,
    imagem: 'https://picsum.photos/300/200?random=16',
    comprado: false
  },
  {
    id: 17,
    nome: '2 Meses de Unha Feita para Juliana',
    valor: 299.90,
    imagem: 'https://picsum.photos/300/200?random=17',
    comprado: false
  },
  {
    id: 18,
    nome: 'Corte de Cabelo do Natã',
    valor: 49.90,
    imagem: 'https://picsum.photos/300/200?random=18',
    comprado: false
  },
  {
    id: 19,
    nome: 'Assinatura de Netflix por 1 Ano',
    valor: 499.90,
    imagem: 'https://picsum.photos/300/200?random=19',
    comprado: false
  },
  {
    id: 20,
    nome: 'Curso de Culinária para Natã',
    valor: 199.90,
    imagem: 'https://picsum.photos/300/200?random=20',
    comprado: false
  },
  {
    id: 21,
    nome: '1 Ano de Massagem para Juliana',
    valor: 999.90,
    imagem: 'https://picsum.photos/300/200?random=21',
    comprado: false
  },
  {
    id: 22,
    nome: 'Aula de Dança para o Casal',
    valor: 299.90,
    imagem: 'https://picsum.photos/300/200?random=22',
    comprado: false
  },
  {
    id: 23,
    nome: 'Sessão de Fotos com Tema Medieval',
    valor: 399.90,
    imagem: 'https://picsum.photos/300/200?random=23',
    comprado: false
  },
  {
    id: 24,
    nome: 'Passeio de Balão ao Pôr do Sol',
    valor: 799.90,
    imagem: 'https://picsum.photos/300/200?random=24',
    comprado: false
  },
  {
    id: 25,
    nome: 'Curso de Stand-up Comedy para Natã',
    valor: 199.90,
    imagem: 'https://picsum.photos/300/200?random=25',
    comprado: false
  },
  {
    id: 26,
    nome: 'Viagem para a Tailândia',
    valor: 10,
    imagem: 'https://picsum.photos/300/200?random=26',
    comprado: false
  }
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

const presentesPaginados = computed(() => {
  const start = paginaAtual.value * itensPorPagina
  const end = start + itensPorPagina
  return presentes.value.slice(start, end)
})

const totalPaginas = computed(() => Math.ceil(presentes.value.length / itensPorPagina))

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
</style>