Am implementat un model ce prezice pretului unui apartament in Bucuresti pe bazanumarului de camere, suprafetei, etajului la care se afla, numarul de etaje 
total pe care le are cladirea, sectorul unde se afla si scorul locatiei. Datele au fost luate din sursa: https://www.kaggle.com/datasets/denisadutca/bucharest-house-price-dataset,
unde se specifica ca au fost colectate in martie 2019 de pe site-ul www.imobiliare.com

Am inceput prin a vizualiza cat de corelate sunt coloane tip feature cu coloana pe care vreau sa o prezic( Pretula apartamentului). Din heatmap-ul generat observ ca variabilele 
'Etaj', 'Total Etaje' sunt foarte putin corelate si variabilele 'Sector' si 'Scor' nu sunt deloc corelate cu variabila pe care vreau sa o prezic. Din aceasta cauza le voi elimina
pentru ca modelul sa nu fie prea complex(sa evit overfitting, varianta mare).

Pentru a rula modelul transform datele categorice in date numerice. Pentru modelul linear aduc datele din coloana 'Suprafata' la o distributie normala standard, pentru o predictie mai buna (regresia lineara utilizeaza o functie pentru predictie, asa ca datele ar trebui sa fie mai liniare). Sterg valorile prea mari sau prea mici( cele ce sunt la mai mult de 3*std fata de media distributiei) pentru o performanta mai buna a modelului. Aplic 3 algortmi: Regresia Lineara, Regresie Polinomiala si KNN pentru regresie. Observ ca modelul KNN si cel polinomial se comporta cel mai bine. Optimizez hiper-parametrii cu tehnica  GridSearc cu Cross-Validation, deaorece acesti parametrii nu pot fi rafinati in procesul de invatare. Impart training set-ul in 6 parti si testez modelul pe fiecare combinatie de parametrii. 

Observ ca modelul polinomial se comporta putin mai bine si il aleg pe acesta cu gradul functiei egal ca fiind modelul potrivit pentru aceasta problema. Obtin un r2-score( raportul dintre valorile obtinute si valorile adevarate) de 0.6513.
