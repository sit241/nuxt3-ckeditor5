<script>
  // pages/sample-editor.vue

  export default {
    data() {
      return {
        editorInput:
          '<p>Однажды жил на свете мальчик, сильный и смелый. И он<span class="green difference">,</span> как и любой мальчик<span class="green difference">,</span> рос<span class="red difference pair1">.</span><span class="green difference pair2">,</span> <span class="red difference pair1">П</span><span class="green difference pair2">п</span>остепенно превращаясь сначала в подростка, а потом и в юношу<span class="red difference pair1">.</span><span class="green difference pair2">,</span> <span class="red difference pair1">К</span><span class="green difference pair2">к</span>оторый хотел<span class="red difference">,</span> победить дракона. Банально? Давайте обсудим это после вашего первого дракона. Я с радостью посмотрю<span class="green difference">,</span> как вы с ним сразитесь, а после порассуждае<span class="red difference pair1">те</span><span class="green difference pair2">м</span> о банальности этого события.<span class="red difference"> </span></p><p>А пока вернемся к мальчику, то есть уже юноше. Можно смело сказать<span class="green difference">,</span> что в его жизни детство уже кончилось. Каждый день он тренировался и оттачивал своё мастерство. Ведь <span class="red difference">э</span>то<span class="red difference"> то</span>лько в сказках с драконом можно поговорить по душам. В реальной жизни этот монстр сразу же тобой отобедает.<span class="red difference"> </span></p><p>Долгие дни, недели<span class="green difference">,</span> месяцы<span class="green difference">,</span> и вот наконец годы он тренировался<span class="red difference pair1">.</span><span class="green difference pair2">,</span> <span class="red difference pair1">П</span><span class="green difference pair2">п</span>ока во всём королевстве не нашлось никого<span class="green difference">,</span> кто смог бы его победить. Тогда он и понял, что момент настал. Следующая цель<span class="red difference">,</span> <span class="red difference pair1 highlighted">это</span><span class="green difference pair2 highlighted">—</span> его мечта. Дракон. То<span class="green difference">,</span> к чему он так долго стремился.<span class="red difference"> </span></p><p>В королевстве устроили большой праздник по этому поводу<span class="red difference pair1">,</span><span class="green difference pair2">:</span> лучший из лучших идет становится легендой, драконоборцем. Под самый конец праздника, когда нашему герою нужно было уходить, а большинство празднующих уже забыли<span class="green difference">,</span> по какому случаю собрались<span class="red difference pair1">.</span><span class="green difference pair2">,</span> <span class="red difference pair1">К</span><span class="green difference pair2">к</span>ороль отвёл юношу в сторону и сказал.<span class="red difference"> </span></p><p>— Не всегда мы находим дракона там<span class="green difference">,</span> где ищем.<span class="red difference"> </span></p>',
      };
    },
  };
</script>

<template>
  <rich-editor
    v-model="editorInput"
    @input="(event) => (editorInput = event)"
  />

  <div>
    <div class="container mt-3">
      <div class="row">
        <h2 class="col-md-12">Output</h2>
        <div>{{ editorInput }}</div>
      </div>
    </div>
    <div class="container mt-3">
      <div class="row">
        <h2 class="col-md-12">Preview</h2>
        <div v-html="editorInput"></div>
      </div>
    </div>
  </div>
</template>

<style>
  :root {
    --primary-color: #ffffff;
    --primary-color-grey: #000000;
    --colot-text: #000000;
    --invert: #fff;
    --colot-text2: #fff;
    --invert2: #000;
    --primary-color2: #000000;

    --quasar-dark-grey-color: #1d1d1d;

    --secondary-color: #6c757d;
    --accent-color: #17a2b8;
    --success-color: #28a745;
    --info-color: #03a9f4;
    --warning-color: #ffc107;
    --danger-color: #dc3545;
    --light-color: #f8f9fa;
    --dark-color: #343a40;
    --dark-real: #000000;
    --white-real: #ffffff;
  }

  .red {
    padding: 0 5px;
    background-color: var(--danger-color);
  }

  .green {
    padding: 0 5px;
    background-color: var(--success-color);
  }

  .difference {
    cursor: pointer;
  }

  .highlighted {
    background-color: transparent;
    border: 3px solid var(--warning-color);
    padding: 0 2px;
    padding-top: 0;
  }

  .highlighted.green {
    background-color: var(--success-color);
  }

  .highlighted.red {
    background-color: var(--danger-color);
  }

  .highlighted.pair1 {
    border: 3px solid var(--warning-color);
    border-right: none;
    padding-right: 5px;
  }

  .highlighted.pair2 {
    border: 3px solid var(--warning-color);
    border-left: none;
    padding-left: 5px;
  }
</style>
