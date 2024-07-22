# Rodolphe
- A part quelques petits détails sur le nesting, ou de petites erreurs (sûrement d'inattention) dans tes sélecteurs, c'est du très bon travail. Et je trouve ça plutôt joli.
- Git : Pense à ton fichier `.gitignore` dans tes projets, notamment pour ne pas versionner la conf de ton IDE (ici le dossier `.idea`)
- HTML
	- La partie HTML est très bien pas grand chose à redire.
- SCSS
	- Bon usage des partials, notamment le `font-family`. Par contre, tu n'utilises pas les variables, ensuite, dans ton fichier scss principal.
	```scss
	body{
	  background-color: $primary-color1;
	  font-family: 'Montserrat', monospace;
	}
	//Deviendrait
	body{
	  background-color: $primary-color1;
	  font-family: $font-family-secondary, monospace;
	}
	```
	- Pour ton burger menu, tu fais des règles sur les `li` alors que tu n'en utilises pas dans ton HTML. Le display `inline-block` sur tes liens devrait suffire. Une autre solution aurait pu être de faire un `display: flex;` sur ta div `#burger`.
	-  Tu devrais abuser un peu plus du nesting, c'est plus agréable :
		```scss
		.presentation>img {
		  width: 50%;
		  border-radius: 5px;
		  border: groove 8px $secondary-color3;
		}
		.presentation {
		  display: flex;
		  align-items: center;
		  flex-direction: row;

		}
		// Devient
		.presentation {
		  display: flex;
		  align-items: center;
		  flex-direction: row;

			>img {
			  width: 50%;
			  border-radius: 5px;
			  border: groove 8px $secondary-color3;
			}
		}
	```

-
	- Même principe pour ton `#portfolio`, ton form, ton block_cta, et idem dans ta media query. Ca rendra ton code plus lisible et simple à maintenir.
	-  De plus, je te conseille de mettre des espaces dans tes sélecteurs quand c'est possible (exemple entre les chevrons quand tu select les enfants : ` > `).

- Responsivité :  Très bien (burger, images, et section "about")
