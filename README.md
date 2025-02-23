# Ripristino CUID con Settore 0 Blocco 0 Errato e Key Sconosciute  

## Requisiti  
- **Linux**  
- **Windows**  
- **Lettore NFC ACR122U**  
- **Fortuna**  

## Istruzioni  
È inclusa anche una guida in PDF con foto. Puoi trovarla [qui](./FixMagicTagGuide.pdf).  


### 1. Preparazione su Linux  
1. Avviare Linux e scaricare **MFOC**:  
   ```bash
   git clone https://github.com/GioeleGregorini/fixmagictag
   cd fixmagictag
   ```
2. Compilare e installare MFOC:  
   ```bash
   autoreconf -is
   ./configure
   make && sudo make install
   ```

### 2. Esecuzione di MFOC  
1. Aprire il terminale nella cartella del progetto.  
2. Collegare il lettore **ACR122U** e appoggiare la carta NFC.  
3. Eseguire il seguente comando:  
   ```bash
   mfoc -P 50 -T 30 -O card.mfd
   ```
4. Se MFOC trova le chiavi, chiudere il terminale e spostare il file `card.mfd` su **Windows**.  

### 3. Uso di MifareOneTool su Windows  
1. Scaricare **MifareOneTool**:  
   [Download](https://github.com/xavave/MifareOneTool-English/releases/download/1.8/MifareOneTool.zip)  
2. Estrarre e avviare il software con il lettore **ACR122U** collegato.  
3. Confermare l'installazione dei driver.  
4. Chiudere **MifareOneTool**, scollegare e ricollegare **ACR122U**.  
5. Avviare nuovamente il programma.  

### 4. Ripristino della Carta  
1. Selezionare **Copy card mode** e cliccare su **Scan card**.  
2. Se le informazioni della carta vengono lette correttamente, procedere.  
3. Accedere alla **Advanced mode of operation**.  
4. Selezionare **MFF08 CUID repair**.  
5. Indicare il file `card.mfd`.  
6. Attendere circa 1 minuto. Se tutto è andato a buon fine, la **MAGIC CARD** sarà ripristinata.  
