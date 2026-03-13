# Includes
# Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:50170/) and see what you can discover.
# Solución
picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}
la primera parte de la bandera esta en : view-source:http://saturn.picoctf.net:50170/style.css
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
la segunda parte de la bandera esta en : view-source:http://saturn.picoctf.net:50170/script.js
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
# Notas
# Referencias
