<template>
  <div>
  <my-header :cartItemCount="cartItemCount"></my-header>
    <div class="row">
      <div class="col-md-10 col-md-offset-1 ml-3">
        <div class="panel panel-info">
          <div class="panel-body">
            <div class="form-group ml-3">
              <div class="col-md-12">
                <h4 class="mt-3"><strong>Информация для оформления</strong></h4>
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6">
                <strong>Имя:</strong>
                <input v-model.trim="order.firstName" class="form-control" />
              </div>
              <div class="col-md-6">
                <strong>Фамилия:</strong>
                <input v-model.trim="order.lastName" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6"><strong>Aдресс:</strong></div>
              <div class="col-md-6">
                <input v-model.trim="order.address" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6"><strong>Город:</strong></div>
              <div class="col-md-6">
                <input v-model.trim="order.city" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-2">
                <strong>Область:</strong>
                <select v-model="order.state" class="form-control">
                  <option disabled value="">Область</option>
                  <option v-for="(state, key) in states" v-bind:value="state">
                  {{key}}
                  </option>
                </select>
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-2 col-md-offset-4">
                <strong>Индекс:</strong>
                <input v-model.number="order.zip"
                   class="form-control"
                   type="number"/>
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6 boxes">
                <input type="checkbox"
                       id="gift" value="true"
                                 v-bind:true-value="order.sendGift"
                                 v-bind:false-value="order.dontSendGift"
                                 v-model="order.gift">
                <label for="gift">Покупка в подарок?</label>
              </div>
            </div><!-- end of form-group -->
            <div class="form-group">
              <div class="col-md-6 boxes">
                <input type="radio"
                       id="home"
                       v-bind:value="order.home"
                       v-model="order.method">
                <label for="home">Домашний адрес</label>
                <input type="radio"
                       id="business"
                       v-bind:value="order.business"
                       v-model="order.method">
                <label for="business">Рабочий адрес</label>
              </div>
            </div><!-- end of form-group-->
            <div class="form-group">
              <div class="col-md-6">
                <button type="submit" class="btn btn-primary submit" v-on:click="submitForm">Оформить заказ</button>
              </div><!-- end of col-md-6-->
            </div><!-- end of form-group-->
          </div><!--end of panel-body-->
        </div><!--end of panel panel-info-->


      </div><!--end of col-md-10 col-md-offset-1-->
    </div><!--end of row-->
  </div>
</template>
<script>
import MyHeader from './Header.vue';
export default {
  name: 'Form',
  props: ['cartItemCount'],
  data () {
    return {
      states: {
        Московская: 'Московская',
        Ленинградская: 'Ленинградская',
        Тверская: 'Тверская',
        Ростовкая: 'Ростовская',
        Кемеровкая: 'Кемеровская'
      },
      order: {
        firstName: '',
        lastName: '',
        address: '',
        city: '',
        zip: '',
        state: '',
        method: 'Home Address',
        business: 'Business Address',
        home: 'Home Address',
        gift:'',
        sendGift: 'Send As A Gift',
        dontSendGift: 'Do Not Send As A Gift'
      }

    }
  },
  components: { MyHeader },
  methods: {
    submitForm() {
      alert('Submitted');
    }
  }
}
</script>
<style scoped>
</style>
