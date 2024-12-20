Co je problém producent-konzument?
Problém producent-konzument je klasické úkoly synchronizace v operačních systémech. Zahrnuje dva typy procesů:

Producent - vytváří data/práce
Konzument - zpracovává data/práce
Tyto procesy sdílejí společný buffer nebo datovou strukturu. Hlavní výzvy spočívají v tom, jak správně koordinovat producenty a konzumenty tak, aby se vyhnuli problémům jako nerovnováze dat.

Klíčové body k považování
Producent nesmí přidat data do plného bufferu (přeplnění)
Konzument nesmí odebrat data z prázdného bufferu (přebytek)
Musí být zajištěn vzájemný vý exclusivity při přístupu k bufferu
Reálný příklad
Můžeme si představit tento problém jako restauraci:

Producenti jsou kuchyňští pracovníci, kteří připravují jídlo podle objednávek
Sdílený buffer je fronta objednávek nebo systém lístku
Konzumenti jsou číšníci/servíři, kteří odebrou objednané jídlo z fronty
Řešení problému
Typické řešení používá semafory:

Semafory plných míst (Full) - počítá plná místa v bufferu
Semafory prázdných míst (Empty) - počítá volná místa v bufferu
Mutex - pro vzájemný vý exclusivity
Producenti a konzumenti pak používají operace wait() a signal() na těchto semaforách k omezení přístupu k bufferu.
