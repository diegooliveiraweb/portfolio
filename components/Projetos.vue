<template>
    <div class="flex flex-col h-screen w-full justify-center items-center overflow-x-hidden relative z-10">
      
      <div class="p-8 max-w-screen-lg z-20">
          <h1 class="text-4xl xl:text-5xl text-white font-bold text-center mb-3">Projetos</h1>
      </div>
      <span class="block h-10 w-10 bg-contain cristal absolute top-10 left-5"></span>
      <span class="h-52 w-52 bg-contain cristal absolute top-36 left-2 cristal-big hidden lg:block"></span>
      <span class="block h-10 w-10 bg-contain cristal absolute top-10 right-5"></span>
      <div class="container">
        <div class="p-5 xl:p-0 grid lg:grid-cols-2 xl:grid-cols-3 gap-4 2xl:gap-7 mb-6">
            <div class="rounded-xl overflow-hidden relative project-post" v-for="p in projetos" :key="p.id">
                <video autoplay="true" loop muted>
                    <source :src="p.src" type="video/mp4">
                </video>
                 <div class="overlay absolute top-0 left-0 w-full h-full bg-[rgba(0,0,0,0.6)] flex items-center justify-center">
                    <div class="content p-4 xl:p-5">
                        <h4 class="text-xl text-white mb-3 font-bold" v-text="p.title"></h4>
                        <p class="text-xs lg:text-sm text-white" v-text="p.description"></p>
                        <div class="flex gap-2 mt-5">
                            <a :href="p.url" target="_blank" rel="external" class="px-4 py-1 bg-green-600 bg-[url('~/assets/img/cristal.png')] bg-cover bg-center text-black font-medium rounded-xl transition ease-in-out hover:scale-105 duration-300">Visitar</a>
                        </div>
                    </div>
                </div>
            </div>
           
        </div>
        <div class="text-center">
            <button class="w-full sm:w-auto px-4 py-2 bg-green-600 text-white mx-auto text-lg">Ver mais</button>
        </div>
      </div>
  </div>
</template>
<script>
export default {
    name: 'BlogComponent',

    data() {
        return {
            projetos:[
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/move-itaigara.mp4', title: 'Move Itaigara', description: 'Move Itaigara - Apartamentos de 3 quartos (suíte) com lavabo e 2 quartos (suíte) que faltava no Itaigara em Salvador.', url: 'https://moveitaigara.com.br/'},
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/blue-barra.mp4', title: 'BLue Barra', description: 'Seja para morar ou para investir, o Blue Barra é uma excelente opção para sua vida...', url: 'http://www.bluebarra.com.br/'},
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/feirao-semana-tem-mais.mp4', title: 'Feirão: Semana Tem Mais', description: 'Casas e apartamentos, com preços imperdíveis, no endereço que você procura.', url: 'http://estacao1construtora.com.br/feirao-semana-tem-mais/'},
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/horto-concept.mp4', title: 'Horto Concept', description: 'Projeto inovador e exclusivo, inspirado no design, bom gosto e arquitetura autoral.', url: 'https://hortoconcept.com.br/'},
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/vivace-sim.mp4', title: 'Vivace SIM', description: 'O Vivace SIM dispõe de casas com 2/4 e uma infraestrutura completa de lazer para você viver os melhores momentos da vida, com a sua família.', url: ''},
                {id:0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/paradiso-papagaio.mp4', title: 'Paradiso Papagaio', description: ' E é pensando nos seus melhores momentos que o Paradiso Papagaio conta com uma infraestrutura completa de lazer.', url: ''},
            ]
        }
    },
}
</script>
<style>
    .overlay{
        display: none;
    }
    .project-post:hover .overlay{
        display: flex;
    }
</style>