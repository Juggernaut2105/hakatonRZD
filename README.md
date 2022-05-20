# hakatonRZD
# Проект анализа станционных операций с ж/д вагонами.
# Итоговая презентация.pptx

(рабочие базы данных здесь не вложены, т.к. превышают допустимый размер)
список рабочих нотбуов, предназначенных для решения отдельных подзадач проекта:

 1
op34_time_calc.ipynb
Из всех событий в исходной базе(statistics-07-20.csv) сформировать записи, содержащие информацию о длительности каждого законченного цикла обмена грузами между вагоном и станцией. Необходимое время для обработки базы составляет 10часов.

2
op34_firstbase.ipynb
Скрипт для обработки первой базы “VIVSD_ASOUP_V_OPER_V2.3DAYS.600000-616000.hashed.1.csv”; 
назначение аналогично скрипту op34_time_calc.ipynb, но реализовано значительно меньше проверок. Необходимое время работы - несколько минут.

3
DS-1.ipynb
Статистический анализ (гистограммы) анализа длительности операций по 4м выборочным станциям

4
DS-2.ipynb
Статистический анализ (гистограммы) анализа длительности операций по полному набору данных

5
Хакатон(static).ipynb
Анализ одномерных данных и графическое представление. Сделана попытка реализаций подсчета времени м/д операциями, с применением встроенных средств Pandas(alfa-verion)

6
Probability algorithm Max Andriichuk.ipynb
Реализован алгоритм вычисляющии самую популярную операцию на станции после текущей. После этого переходит к следующей самой популярной операции прибавляя ее среднюю длительность. И так далее, пока не наткнется на операцию 4 "ВКЛЮЧЕНИЕ В ПОЕЗД" или NAN.  В итоге суммирует вероятность этой цепочки и общую предполагаемую длительность.

7
RZD_graphs.ipynb
Содержит функцию для построения графа последовательности операций для заданного вагона на заданной станции

8
RZD_chains.ipynb
Содержит функцию определения последовательностей операций (цепочки) вагонов на всех станциях. Жизненный цикл вагона на станции заканчивается, когда признак Код операции ВМ АСОУП == nan (эти циклы хорошо видны на графах).
По сформированным цепочкам (топ 5 по популярности) построены графики распределения продолжительности цепочки в разрезе рода вагона и в разрезе рейтинга станции (частые-редкие)
