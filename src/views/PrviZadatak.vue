<template>
	<v-container fill-height fluid class="background">
		<v-row>
			<v-col cols="12">
				<v-card class="pa-3" outlined width="600px">
					<v-card-title>Dodaj studenta</v-card-title>
					<v-card-text>
						<v-form>
							<v-text-filed label="Ime"></v-text-filed>
							<v-text-filed label="Prezime" ></v-text-filed>
							<v-text-filed label="Broj dolazaka (maximalno 15)" ></v-text-filed>
							<v-text-filed label="Rezultat prvog kol (40)" ></v-text-filed>
							<v-text-filed label="Rezultat drugog kol (40)" ></v-text-filed>
							<v-text-filed label="Kontinuirano pracenje (20)" ></v-text-filed>

						</v-form>
					</v-card-text>
					<v-card-actions>
						<v-btn
							color="black"
							class="white--text"
							elevation="0"
							@click="obrisiSveUnesenePodatke">
							BRISI PODATKE
						</v-btn>
						<v-btn style="position: static; right: auto; color: aqua; border: 5px green; ">Obriši sve</v-btn>
						<v-btn ></v-btn>
						<v-spacer></v-spacer>
					</v-card-actions>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
export default {
	name: "prvi-zadatak",
	data() {
		return {};
	},
	watch: {},
	methods: {
		ocistiFormu() {},
		dodajStudenta() {
			let noviStudent = {
				//Dodaj propertyje
				
			};
			//ovo ne diraj
			let studenti = JSON.parse(localStorage.getItem("studenti"));
			if (!studenti) {
				studenti = [];
			}
			studenti.push(noviStudent);
			localStorage.setItem("studenti", JSON.stringify(studenti));
		},
		obrisiSveUnesenePodatke() {
			localStorage.clear();
		},
	},
};
</script>
