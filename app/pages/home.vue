<template>
  <f7-page>
    <f7-navbar :title="$root.config.title" />
    <f7-block>
      <f7-button big fill raised bg="blue" href="http://buccoliero.com" external>Interventi</f7-button>
    </f7-block>
    <f7-block>
      <f7-button big fill raised bg="green" href="http://buccoliero.com" external>Clienti</f7-button>
    </f7-block>
    <f7-block inner inset>{{$lang('text')}}</f7-block>
  </f7-page>
</template>
