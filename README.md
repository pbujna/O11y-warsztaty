<h1>IM Lab 1</h1>

Stwórz chart przedstawiający max, mean i min dla metryki <i>demo.trans.latency</i>. 
Wizualizacja powinna bazować tylko na danych z datacenter z Tokyo.
Sygnały powinny odróżniać się od siebie kolorami, a całość powinna być przedstawiona w postaci wizualizacji typu <i>Area</i>.

<h1>IM Lab 2</h1>

Na bazie charta z poprzedniego laba przygotuj detector, który będzie alertował nagłą zmianę w sygnale C (<i>demo.trans.latency - Maximum</i>). Alert powinien być wywołany w momencie, w którym wartości zebrane przez ostatnią minutę mają odchylenie standardowe 2,5 razy większe lub mniejsze od średniej z poprzednich 5 minut. <i>Clear threshold</i> dopasuj według własnego uznania.

<h2>Rozwiązanie IM Lab 1</h2>

1. W zakładce <i>Metric Finder</i> znajdź i wybierz metrykę <i>demo.trans.latency</i>.
2. Zidentyfikuj sygnał A i poprzez przycisk <i>Add filter</i> wybierz <i>demo.datacenter:Tokyo</i>.
3. Dla tego samego sygnału naciśnij przycisk <i>Add analytics</i> i wybierz funkcję <i>Mean</i>, a następnie opcję <i>Mean:Aggregation</i>. Pole <i>Group by</i> pozostaw puste.
4. Dla tego samego sygnału naciśnij trzy kropki znajdujące się po prawej stronie i wybierz opcję <i>Clone</i>.
5. Wynikiem opcji <i>Clone</i> jest pojawienie się kopii syngału A w postaci sygnału B (może pojawić się też inna litera w zależności od tego czy wcześniej dodawałeś lub usuwałeś inne sygnały).
6. Dla sygnału B zmień funkcję z <i>Mean</i> na <i>Minimum</i> -> <i>Minimum:Aggregation</i>. Pole <i>Group by</i> pozostaw puste.
7. Sklonuj sygnał B i dla sygnału C zmień funkcję z <i>Minimum</i> na <i>Maximum</i> -> <i>Maximum:Aggregation</i>. Pole <i>Group by</i> pozostaw puste.
8. Dla sygnału B naciśnij koło zębate znajdujące się po prawej stronie i w sekcji <i>Plot color</i> wybierz dowolny kolor. Po wybraniu koloru zamknij sekcję przyciskiem <i>Close</i>.
9. To samo powtórz dla sygnału C.
10. W zakładce <i>Chart options</i> znajdź opcję <i>Visualization type</i> i wybierz wizualizację typu <i>Area</i>.
11. Zapisz chart wybierając <i>Save as...</i>. W sekcji Chart name wpisz <i>Latency chart [Twoje inicjały]</i>.
12. W kolejnym kroku wybierz <i>New dashboard</i>. W sekcji <i>Name</i> wpisz <i>Latency dashboard [Twoje inicjały]</i>. Resztę pozostaw domyślnie.
13. Wybierz swój nowo stowrzony dashboard i naciśnij <i>Ok</i>.

<h2>Rozwiązanie IM Lab 2</h2>

1. W prawym górnym rogu charta stworzonego na poprzednim labie naciśnij przycik dzwoneczka i wybierz <i>New detector from chart</i>.
2. Jako nazwę podaj <i>Latency Detector [Twoje inicjały]</i> i kliknij <i>Create alert rule</i>.
3. W prawym górnym rogu zmień paramter <i>Time</i> na <i>-15m</i>.
4. W kroku pierwszym naciśnij przycisk dzwoneczka dla sygnału C (jeśli masz inne litery, to zidentyfikuj <i>demo.trans.latency</i> z funkcją <i>Maximum</i>) - w ten sposób definiujemy który sygnał będzie objęty alertem. Naciśnij <i>Proceed to Alert Condition</i>.
5. W kroku drugim wybierz <i>Sudden Change</i>. Naciśnij <i>Proceed to Alert Settings</i>.
6. W kroku trzecim wybierz <i>Show advanced settings</i> - ta opcja pozwala na zdefiniowanie własnych progów. Dla <i>Current window</i> wpisz 1m. Dla <i>Historical window</i> wpisz 5m. Dla <i>Trigger threshold</i> wpisz 2.5. Dla <i>Clear threshold</i> wpisz wartość mniejszą od 2.5 - domyślnie 2. Naciśnij <i>Proceed to Alert Message</i>.
7. W kroku czwartym wybierz <i>Severity</i> na <i>Major</i>. Naciśnij <i>Proceed to Alert Recipients</i>.
8. Możesz pominąć ten krok. Jeśli chcesz otrzymać maila o wywołanym alercie, to w <i>Add recipient</i> wybierz E-mail i wpisz swojego maila. 
9. Naciśnij <i>Proceed to Alert Activation</i>.
10. W sekcji <i>Rule Name</i> wpisz <i>Latency Detector [Twoje inicjały] Rule</i>. Naciśnij <i>Activate Alert Rule</i>.
11. Jeśli nie wpisałeś nic w sekcji <i>Alert Recipients</i> otrzymasz informację <i>Missing Notification Policy</i> - możesz zignorować tą informację i nacisnąć <i>Save</i>.