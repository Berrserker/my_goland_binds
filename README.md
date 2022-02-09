# my_goland_binds

```
<template name=":" value="$NAME$ := $VALUE$$END$" description="Variable declaration :=" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;name&quot;" alwaysStopAt="true" />
  <variable name="VALUE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="bench" value="func Benchmark$NAME$(b *testing.B) {&#10; for i := 0; i &lt; b.N; i++ {&#10; $END$&#10; }&#10;}" description="Benchmark" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;Name&quot;" alwaysStopAt="true" />
  <context />
</template>
<template name="consts" value="const (&#10; $NAME$ = $VALUE$$END$&#10;)&#10;" description="Constants declaration" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;name&quot;" alwaysStopAt="true" />
  <variable name="VALUE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="ctx" value="context.$VALUE$$END$" description="context.*" toReformat="false" toShortenFQNames="true">
  <variable name="VALUE" expression="complete()" defaultValue="Context" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
    <option name="HTTP_CLIENT_ENVIRONMENT" value="true" />
    <option name="REQUEST" value="true" />
  </context>
</template>
<template name="ctxC" value="$NAME$, $NAME$Cancel := context.WithCancel($CONTEXT$)&#10;defer $NAME$Cancel()&#10;$END$" description="context.WithTimeout" toReformat="false" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;ctx&quot;" alwaysStopAt="true" />
  <variable name="CONTEXT" expression="complete()" defaultValue="&quot;context.TODO&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="ctxT" value="$NAME$, $NAME$Cancel := context.WithTimeout($CONTEXT$, $TIME$)&#10;defer $NAME$Cancel()&#10;$END$" description="context.WithTimeout" toReformat="false" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;ctx&quot;" alwaysStopAt="true" />
  <variable name="CONTEXT" expression="complete()" defaultValue="&quot;context.TODO&quot;" alwaysStopAt="true" />
  <variable name="TIME" expression="complete()" defaultValue="&quot;time.Second&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="errr" value="if $ERR$ != nil {&#10; return $RETURN$errors.Wrap($ERR$, &quot;$TEXT$&quot;)$END$&#10;}" description="if err return wraped" toReformat="false" toShortenFQNames="true">
  <variable name="ERR" expression="errorVariable()" defaultValue="&quot;err&quot;" alwaysStopAt="true" />
  <variable name="RETURN" expression="regularExpression(defaultReturnValues, &quot;([^,]*$)&quot;, &quot;&quot;)" defaultValue="" alwaysStopAt="true" />
  <variable name="TEXT" expression="errorVariable()" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="fori" value="for $INDEX$ := 0; $INDEX$ &lt; $LIMIT$; $INDEX$++ {&#10; $END$&#10;}" description="Indexed for loop" toReformat="true" toShortenFQNames="true">
  <variable name="INDEX" expression="" defaultValue="&quot;n&quot;" alwaysStopAt="true" />
  <variable name="LIMIT" expression="" defaultValue="&quot;&quot;" alwaysStopAt="true" />
  <context />
</template>
<template name="forr" value="for $KEY$, $VALUE$ := range $COLLECTION$ {&#10; $END$&#10;}" description="For range loop" toReformat="true" toShortenFQNames="true">
  <variable name="COLLECTION" expression="complete()" defaultValue="&quot;collection&quot;" alwaysStopAt="true" />
  <variable name="KEY" expression="goSuggestVariableName()" defaultValue="&quot;key&quot;" alwaysStopAt="true" />
  <variable name="VALUE" expression="goSuggestVariableName()" defaultValue="&quot;value&quot;" alwaysStopAt="true" />
  <context />
</template>
<template name="func" value="func $NAME$($PARAMS$) ($TYPE_1$, $ERR_TYPE$) {&#10; $END$&#10; return $TYPE_1$, nil&#10;}" toReformat="false" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="" alwaysStopAt="true" />
  <variable name="PARAMS" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <variable name="TYPE_1" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <variable name="ERR_TYPE" expression="errorVariableDefinition(expressionWithErrorResult)" defaultValue="&quot;error&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="if" value="if $PARAMS$ == nil {&#10; $END$&#10;}" description="if" toReformat="false" toShortenFQNames="true">
  <variable name="PARAMS" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="if!" value="if $ERR$ != nil {&#10; $END$&#10;}" description="If error" toReformat="true" toShortenFQNames="true">
  <variable name="ERR" expression="errorVariable()" defaultValue="&quot;err&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO_STATEMENT" value="true" />
  </context>
</template>
<template name="imports" value="import (&#10; &quot;$END$&quot;&#10;)&#10;" description="Imports declaration" toReformat="true" toShortenFQNames="true">
  <context />
</template>
<template name="init" value="func init() {&#10; $END$&#10;}" description="Init function" toReformat="true" toShortenFQNames="true">
  <context />
</template>
<template name="iota" value="const $NAME$ $TYPE$ = iota" description="Iota constant declaration" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;name&quot;" alwaysStopAt="true" />
  <variable name="TYPE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="jsonc" value="'json:&quot;$FIELD_NAME$&quot;'$END$" description="json tag from field name" toReformat="false" toShortenFQNames="true">
  <variable name="FIELD_NAME" expression="camelCase(fieldName())&#9;" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="main" value="func main() {&#10; $END$&#10;}" description="Main function" toReformat="true" toShortenFQNames="true">
  <context />
</template>
<template name="map" value="map[$KEY_TYPE$]$VALUE_TYPE$" description="Map type" toReformat="true" toShortenFQNames="true">
  <variable name="KEY_TYPE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <variable name="VALUE_TYPE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="meth" value="func ($RECEIVER$ *$TYPE_1$) $NAME$($PARAMS$) ($TYPE_1$, $ERR_TYPE$) {&#10; $END$&#10; return $TYPE_1$, nil&#10;}" description="Method" toReformat="true" toShortenFQNames="true">
  <variable name="TYPE_1" expression="complete()" defaultValue="&quot;&quot;" alwaysStopAt="true" />
  <variable name="NAME" expression="" defaultValue="&quot;name&quot;" alwaysStopAt="true" />
  <variable name="RECEIVER" expression="completeSmart()" defaultValue="&quot;s&quot;" alwaysStopAt="true" />
  <variable name="PARAMS" expression="" defaultValue="" alwaysStopAt="true" />
  <variable name="ERR_TYPE" expression="errorVariableDefinition(expressionWithErrorResult)" defaultValue="&quot;error&quot;" alwaysStopAt="true" />
  <context />
</template>
<template name="mkm" value="make(map[$TYPE_1$]$TYPE_2$, $LEN$, $CAP$)$END$" description="make map" toReformat="false" toShortenFQNames="true">
  <variable name="TYPE_1" expression="completeSmart()" defaultValue="" alwaysStopAt="true" />
  <variable name="TYPE_2" expression="completeSmart()" defaultValue="" alwaysStopAt="true" />
  <variable name="LEN" expression="completeSmart()" defaultValue="&quot;0&quot;" alwaysStopAt="true" />
  <variable name="CAP" expression="completeSmart()" defaultValue="&quot;0&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="mks" value="make([]$TYPE_1$, $LEN$, $CAP$)$END$" description="make slice" toReformat="false" toShortenFQNames="true">
  <variable name="TYPE_1" expression="completeSmart()" defaultValue="" alwaysStopAt="true" />
  <variable name="LEN" expression="completeSmart()" defaultValue="&quot;0&quot;" alwaysStopAt="true" />
  <variable name="CAP" expression="completeSmart()" defaultValue="&quot;0&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="p" value="package $NAME$" description="Package declaration" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="printf" value="log.Printf(&quot;$END$&quot;,$VAR$)" description="printf" toReformat="true" toShortenFQNames="true">
  <variable name="VAR" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="slc" value="select {&#10;    case $CHAN1$:&#10;    case $CHAN2$:&#10;    case $CONTEXT$.Done():&#10;    default:&#10;}" description="select" toReformat="false" toShortenFQNames="true">
  <variable name="CHAN1" expression="completeSmart()" defaultValue="&quot;ch1&quot;" alwaysStopAt="true" />
  <variable name="CHAN2" expression="completeSmart()" defaultValue="&quot;ch2&quot;" alwaysStopAt="true" />
  <variable name="CONTEXT" expression="completeSmart()" defaultValue="&quot;ctx&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="st" value="type $TYPE_1$ struct {&#10;    $END$&#10;}" description="struct" toReformat="false" toShortenFQNames="true">
  <variable name="TYPE_1" expression="" defaultValue="&quot;NewMyStruct&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="sw" value="switch $PARAMS$ {&#10;    case $PARAMS_2$:&#10;    case $PARAMS_3$:&#10;    default:&#10;        $END$&#10;}" description="switch" toReformat="false" toShortenFQNames="true">
  <variable name="PARAMS" expression="completeSmart()" defaultValue="true" alwaysStopAt="true" />
  <variable name="PARAMS_2" expression="completeSmart()" defaultValue="" alwaysStopAt="true" />
  <variable name="PARAMS_3" expression="completeSmart()" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
<template name="test" value="func Test$NAME$(t *testing.T) {&#10; $END$&#10;}" description="Test" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;Name&quot;" alwaysStopAt="true" />
  <context />
</template>
<template name="types" value="type (&#10; $END$&#10;)&#10;" description="Types declaration" toReformat="true" toShortenFQNames="true">
  <context />
</template>
<template name="vars" value="var (&#10; $NAME$ = $VALUE$$END$&#10;)&#10;" description="Variables declaration" toReformat="true" toShortenFQNames="true">
  <variable name="NAME" expression="" defaultValue="&quot;name&quot;" alwaysStopAt="true" />
  <variable name="VALUE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context />
</template>
<template name="wrap" value="$END$ errors.Wrap($ERR$, &quot;$TEXT$&quot;)$END$" description="errors.wrap" toReformat="false" toShortenFQNames="true">
  <variable name="ERR" expression="errorVariable()" defaultValue="&quot;err&quot;" alwaysStopAt="true" />
  <variable name="TEXT" expression="errorVariable()" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
```
