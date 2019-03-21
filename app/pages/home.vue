<template>
  <f7-page>
    <f7-navbar :title="$root.config.title" />
    <f7-block>
      <f7-button big fill raised bg="blue" href="/interventi/">Interventi</f7-button>
    </f7-block>
    <f7-block>
      <f7-button big fill raised bg="green" href="/clienti/">Clienti</f7-button>
    </f7-block>
    <f7-block inner inset>{{$lang('text')}}</f7-block>
  </f7-page>
</template>
