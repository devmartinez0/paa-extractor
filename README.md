# INSTRUCTIONS / INSTRUCCIONES
- EN: Just copy this code in your browser console and press ENTER
- ES: Solo tienes que copiar este código en la consola de tu navegador y presiona ENTER

```
// CHANGE THIS IF YOU WANT TO UPDATE THE MAX NUMBER OF RESULTS OBTAINED FROM PAA, DEFAULT IS 100
// CAMBIA ESTE VALOR SI DESEAS ACTUALIZAR LA CANTIDAD MAXIMA DE RESULTADOS OBTENIDOS DE PAA, POR DEFECTO SON 100
const maxResults = 100;

const delay = (ms) => new Promise((res) => setTimeout(res, ms));
let continueProcess = true;
let lastCount = 0;

while (continueProcess) {
  var paa = document.getElementsByClassName("aj35ze");
  for (let i = 0; i < paa.length; i++) {
    console.clear();
    console.log("Getting data. Please wait...");
    console.log("Current result count: " + paa.length);
    if (paa.length >= maxResults) break;
    const element = paa[i];
    element.click();
    await delay(1000);
    element.click();
    await delay(500);
  }
  continueProcess = false;
}
console.clear();
console.log("============== RESULT ==============");
console.log(
  [...document.getElementsByClassName("CSkcDe")]
    .map((x) => x.innerHTML)
    .join()
    .replace(/'/g, "")
    .replace(/,/g, "\n")
);
console.log("==============  END   ==============");
```
