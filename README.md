<meta name='viewport' content='width=device-width, initial-scale=1'/><!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<title>Calcolo Mutuo e Prestito Online | Rata e Ammortamento</title>
<meta name="description" content="Calcolo mutuo e prestito online gratuito. Simula rata mensile, interessi, anticipo e visualizza la tabella di ammortamento completa.">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- CODICE GOOGLE ADSENSE -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3099756567574901"
     crossorigin="anonymous"></script>

<style>
:root{
    --bg: #f6f7fb;
    --card: #ffffff;
    --text: #1b1f2a;
    --muted: #7b8293;
    --primary: #4f7cff;
    --primary2: #2bc0ff;
    --accent: #ff6b6b;
    --shadow: 0 12px 30px rgba(20, 40, 80, 0.12);
    --radius: 14px;
}

*{
    box-sizing: border-box;
}

body{
    font-family: 'Arial', sans-serif;
    background: linear-gradient(135deg, #eef3ff, #f6f7fb);
    margin: 0;
    padding: 0;
    color: var(--text);
}

.container{
    max-width: 1100px;
    margin: 30px auto;
    padding: 20px;
}

.header{
    text-align: center;
    padding: 20px 10px;
}

h1{
    margin: 0;
    font-size: 30px;
    letter-spacing: 0.5px;
}

.subtitle{
    margin-top: 8px;
    color: var(--muted);
    font-size: 16px;
}

.card{
    background: var(--card);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 20px;
    margin-top: 20px;
}

.form-grid{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
}

label{
    font-weight: 600;
    color: var(--text);
    display: block;
    margin-bottom: 6px;
}

input, select{
    width: 100%;
    padding: 12px 14px;
    border-radius: 12px;
    border: 1px solid #d6d9e6;
    background: #fbfbff;
    outline: none;
    transition: border-color .2s ease;
}

input:focus, select:focus{
    border-color: var(--primary2);
    box-shadow: 0 0 0 4px rgba(43, 192, 255, 0.18);
}

button{
    width: 100%;
    padding: 14px;
    border-radius: 12px;
    border: none;
    cursor: pointer;
    font-size: 16px;
    color: #fff;
    background: linear-gradient(135deg, var(--primary), var(--primary2));
    transition: transform .2s ease, opacity .2s ease;
}

button:hover{
    transform: translateY(-2px);
    opacity: 0.98;
}

.result{
    margin-top: 20px;
    padding: 18px;
    background: linear-gradient(135deg, #eef7ff, #f4fbff);
    border-radius: 12px;
    border: 1px solid #dce9ff;
}

.result strong{
    color: var(--text);
}

.ads{
    margin: 28px 0;
    padding: 20px;
    background: #f1f1f1;
    text-align: center;
    color: #666;
    border-radius: 12px;
}

.table-wrapper{
    overflow-x: auto;
    margin-top: 10px;
}

table{
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
    font-size: 14px;
}

table th, table td{
    border: 1px solid #e4e7f2;
    padding: 10px 8px;
    text-align: right;
}

table th{
    background: linear-gradient(135deg, #f0f4ff, #ffffff);
    color: #4a4f6b;
}

table tr:nth-child(even){
    background: #fbfbff;
}

.table-title{
    margin-top: 20px;
    font-size: 22px;
    color: var(--text);
    text-align: center;
}

.footer{
    text-align: center;
    font-size: 13px;
    color: #777;
    margin-top: 40px;
}

/* Responsive */
@media (max-width: 768px){
    .form-grid{
        grid-template-columns: 1fr;
    }
    h1{
        font-size: 26px;
    }
}
</style>
</head>

<body>
<div class="container">

    <div class="header">
        <h1>Calcolo Mutuo e Prestito Online</h1>
        <div class="subtitle">Simula rata, interessi e ammortamento in modo semplice e veloce.</div>
    </div>

    <div class="card">
        <div class="form-grid">
            <div>
                <label>Tipo di finanziamento</label>
                <select id="tipo">
                    <option value="mutuo">Mutuo</option>
                    <option value="prestito">Prestito personale</option>
                </select>
            </div>

            <div>
                <label>Tipo di tasso</label>
                <select id="tipotasso">
                    <option value="fisso">Fisso</option>
                    <option value="variabile">Variabile (simulato)</option>
                </select>
            </div>

            <div>
                <label>Importo totale (€)</label>
                <input type="number" id="importo" placeholder="Es. 200000">
            </div>

            <div>
                <label>Anticipo (€)</label>
                <input type="number" id="anticipo" placeholder="Es. 20000">
            </div>

            <div>
                <label>Tasso annuo (%)</label>
                <input type="number" step="0.01" id="tasso" placeholder="Es. 2.50">
            </div>

            <div>
                <label>Durata (anni)</label>
                <input type="number" id="anni" placeholder="Es. 25">
            </div>
        </div>

        <button onclick="calcola()">Calcola</button>

        <div id="risultato" class="result" style="display:none;"></div>
    </div>

    <div class="ads">Spazio Google AdSense</div>

    <div class="table-title">Tabella di Ammortamento</div>
    <div class="table-wrapper">
        <table id="ammortamento"></table>
    </div>

    <div class="ads">Spazio Google AdSense</div>

    <p style="text-align:center; color:#666; margin-top: 20px;">
        Questo strumento consente di simulare un mutuo o prestito personale, calcolando la rata,
        gli interessi totali e la tabella di ammortamento mensile.
    </p>

    <div class="footer">
        © 2026 - Calcolo Mutuo Online
    </div>
</div>

<script>
function calcola() {
    let importo = parseFloat(document.getElementById("importo").value);
    let anticipo = parseFloat(document.getElementById("anticipo").value) || 0;
    let tasso = parseFloat(document.getElementById("tasso").value);
    let anni = parseInt(document.getElementById("anni").value);
    let tipoTasso = document.getElementById("tipotasso").value;

    if (isNaN(importo) || isNaN(tasso) || isNaN(anni)) {
        alert("Compila tutti i campi correttamente");
        return;
    }

    let capitale = importo - anticipo;
    let r = (tasso / 100) / 12;
    let n = anni * 12;

    // Ammortamento
    let rata = capitale * (r / (1 - Math.pow(1 + r, -n)));
    let totale = rata * n;
    let interessi = totale - capitale;

    document.getElementById("risultato").style.display = "block";
    document.getElementById("risultato").innerHTML =
        "<strong>Capitale finanziato:</strong> " + capitale.toFixed(2) + " €<br>" +
        "<strong>Rata mensile:</strong> " + rata.toFixed(2) + " €<br>" +
        "<strong>Totale interessi:</strong> " + interessi.toFixed(2) + " €<br>" +
        "<strong>Totale da restituire:</strong> " + totale.toFixed(2) + " €";

    // Tabella
    let tabella = "<tr><th>Mese</th><th>Rata</th><th>Interessi</th><th>Capitale</th><th>Residuo</th></tr>";
    let residuo = capitale;

    for (let i = 1; i <= n; i++) {
        let interesse = residuo * r;
        let quotaCapitale = rata - interesse;
        residuo -= quotaCapitale;

        tabella += "<tr>" +
            "<td>" + i + "</td>" +
            "<td>" + rata.toFixed(2) + "</td>" +
            "<td>" + interesse.toFixed(2) + "</td>" +
            "<td>" + quotaCapitale.toFixed(2) + "</td>" +
            "<td>" + Math.max(residuo, 0).toFixed(2) + "</td>" +
            "</tr>";
    }

    document.getElementById("ammortamento").innerHTML = tabella;
}
</script>

</body>
</html>