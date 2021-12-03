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
        firstname: 'prénom',
        lastname: 'nom',
        date_of_birth: 'date naissance',
        date_of_death: 'date mort',
        job: 'rôle',
        nb_rescues: 0,
        picture: '#',
        description: 'une **description**'
      },
    }
  },
}
</script>

<style>

</style>