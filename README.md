### Como funciona esto : 

La vulnerabilidad me permite tener acceso ilimitado y gratis a la api de Google translate. Esto me permite implementar de manera fácil y rápida la api en cualquier aplicación (ya sea web o móvil).

Esto funciona gracias a un posible error de autenticación, ya que podemos realizar llamadas a la api sin ningún tipo de token o algún tipo de autorización.



<br/>

### Ejemplos de uso :


```python

data = Translator(jsonSerialize=True).translate({
   'sl':'auto',
   'tl':'es',
   'text':"Hello world,my name is SrRiuz"
})

#{
#  "trans": "Hola mundo, mi nombre es SrRiuz",
#  "orig": "Hello world,my name is SrRiuz",
#  "lenguaje": {
#    "sl": "auto",
#    "tl": "es"
#  }
#}



```

<br/>


Tambien permite la auto deteccion de idioma,tan solo basta poner "auto" en el parametro "trans".  ```{ "trans":"auto" } ``` :
<br/>

```python
translator = Translator(jsonSerialize=True).translate({
  'sl':'auto',
  'tl':'ja',
  'text':'Lorem Ipsum is simply dummy text of the printing and typesetting industry. '
})  

#{
#  "trans": "Lorem Ipsumは、印刷および植字業界の単なるダミーテキストです。",
#  "orig": "Lorem Ipsum is simply dummy text of the printing and typesetting industry.",
#  "lenguaje": {
#    "sl": "auto",
#    "tl": "ja"
#  }
#}

```


<br/>


Si el parametro ```jsonSerialize``` no es proporcionado por defecto se retornara el objeto y no un json
<br/>

```python
data = Translator().translate({
   'sl':'auto',
   'tl':'ja',
   'text':'Lorem Ipsum is simply dummy text of the printing and typesetting industry.'
})

# <ResponseTranslate text='Lorem Ipsumは、印刷および植字業界の単なるダミーテキストです。...' sl='auto' lt='ja' error='False'>
```


