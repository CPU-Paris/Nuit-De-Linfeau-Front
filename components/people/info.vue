<template>
  <div>
    <div>
        <p>{{result.firstname}} {{result.lastname}} / {{result.date_of_birth}} - {{result.date_of_death}}</p>

        <p>{{result.job}}</p>
        
        <p>{{ $tc('sauvetages-effectues', result.nb_rescues, {nb: result.nb_rescues }) }}</p>
    </div>

    <div>

        <img :src="result.picture">
    </div>

    <div>
        <adminMarkdown :md="result.description" noEdit/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: {
        firstname: $t('prenom'),
        lastname: $t('nom'),
        date_of_birth: $t('date-naissance'),
        date_of_death: $t('date-mort'),
        job: $t('role'),
        nb_rescues: 0,
        picture: '#',
        description: $t('une-description')
      },
    }
  },
}
</script>

<style>

</style>