Am implementat un model ce prezice pretului unui apartament in Bucuresti pe bazanumarului de camere, suprafetei, etajului la care se afla, numarul de etaje 
total pe care le are cladirea, sectorul unde se afla si scorul locatiei. Datele au fost luate din sursa: https://www.kaggle.com/datasets/denisadutca/bucharest-house-price-dataset,
unde se specifica ca au fost colectate in martie 2019 de pe site-ul www.imobiliare.com.
Am inceput prin a vizualiza cat de corelate sunt coloane tip feature cu coloana pe care vreau sa o prezic( Pretula apartamentului). Din heatmap-ul generat observ ca variabilele 
'Etaj', 'Total Etaje' sunt foarte putin corelate si variabilele 'Sector' si 'Scor' nu sunt deloc corelate cu variabila pe care vreau sa o prezic. Din aceasta cauza le voi elimina
pentru ca modelul sa nu fie prea complex(sa evit overfitting, varianta mare).
