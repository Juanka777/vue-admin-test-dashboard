<template>
  <section class="section is-title-bar">
    <div class="level">
      <div class="level-left">
        <div class="level-item">
          <ul>
            <li v-for="(title,index) in titleStack" :key="index">{{ title }}</li>
          </ul>
        </div>
      </div>
      <div class="level-right">
        <div class="level-item">
          <div class="button is-primary is-beefy" @click="personNewModal=true">
              <b-icon icon="account-multiple" custom-size="default" class="has-fill-white"/>
              <span class="has-text-white-ter">Create a new Person</span>
          </div>
        </div>
      </div>
    </div>

    <!-- New Person Modal -->
    <create-new-person
        :isActive.sync="personNewModal"
        @close="personNewModal=false">
    </create-new-person>
  </section>
</template>

<script>
import createNewPerson from '@/components/CreateNewPerson.vue'

export default {
  name: 'TitleBar',
  props: {
    titleStack: {
      type: Array,
      default: () => []
    }
  },
  components:
  {
    createNewPerson
  },
  data () {
    return {
      personNewModal: false
    }
  }
}
</script>
