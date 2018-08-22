<template>
  <div class="row" id="translateForm">
    <div class="col-md-6 col-md-offset-3">
      <form class="well form-inline" v-on:submit="formSubmit">
        <input class="form-control" type="text" name="" value="" v-model="textToTeanslate" placeholder="输入需要翻译的内容">
        <select class="form-control" name="" v-model="language">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Janpense</option>
        </select>
        <input type="submit" class="btn btn-primary" name="" value="翻译">
      </form>

    </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data: function () {
    return {
      textToTeanslate: '',
      language: ''
    }
  },
  methods: {
    formSubmit: function(e){
      // alert(this.textToTeanslate)
      this.$emit("formSubmit",this.textToTeanslate,this.language);
      e.preventDefault();
    }
  },
  created: function(){
    this.language='en'
  }
}
</script>

<style>

</style>
