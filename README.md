# "Analysis of the Results of the “Website Redesign A/B Test”
 This notebook contains a comprehensive analysis of the results of an A/B test of a new webpage design.
Objective: To determine whether the new design improved conversion rates, session duration, and page views. 

Project Objective:
To evaluate the effectiveness of the new website design (treatment group) compared to the current design (control group). The main question is: Did the new design improve key user behavior metrics, specifically:
Conversion rate (converted) – Did the user complete the target action?
Session duration (session_duration) – how many minutes the user spent on the site.
Number of pages viewed (pages_visited) – page depth.
Additionally – segmentation by age groups and statistical confirmation of the significance of differences.

Data:
Sample size: 10,000 users
control – 5,013
treatment – 4,987
Features: user_id, variant, converted, session_duration, pages_visited, age
The data was pre-cleaned and checked for missing values and outliers.

Analysis Steps:
Calculation of Key Metrics
Number of conversions, average session duration, average number of pages—separately for each group.
Statistical testing
Z-test of proportions for conversion.
Welch’s t-test (independent samples, unequal variances) for session_duration and pages_visited.
Significance level α = 0.05.
Segmentation by age
Groups: <25, 25–34, 35–44, 45+.
Tests were repeated for each group.

Outlier analysis:
Interquartile range (IQR) method.
Boxplot for visualizing distributions.
Power Analysis
For the group where the conversion rate was found to be insignificant (25–34), the required sample size was calculated.
Visualization
Dashboard in Python (matplotlib) and Excel.
Group comparison charts, p-value tables, distributions by age segments.

According to the analysis results, the overall metrics showed that the conversion rate in the Control group was 10.65%, and in the Treatment group – 14.34%, meaning the difference is +3.69 percentage points, which corresponds to a relative increase of 34.6%. The average session duration increased from 5.03 minutes in the Control group to 7.02 minutes in the Treatment group, i.e., +1.99 minutes or +39.6%. The average number of pages viewed increased from 2.98 to 5.01, a difference of +2.03 pages, representing a relative change of +68.1%.

Statistical tests confirmed the significance of these differences. For conversion, the Z-test yielded a statistic of z = -5.573 with a p-value < 0.001, which is significant. Session duration according to the T-test: t = -44.341, p-value < 0.001 – significant. Number of pages: t = -51.256, p-value < 0.001 – significant. Thus, all three metrics improved in a statistically significant manner.

Segmentation by age showed that for the group aged 25 and under, the conversion rate was 9.9% in the control group and 14.7% in the test group, p-value = 0.0053 – significant. For the 25–34 age group, the conversion rate was 11.3% versus 13.3%, p-value = 0.1491 – not significant. For the 35–44 age group: 10.3% versus 15.5%, p-value = 0.0003 – significant. For the 45+ age group: 10.7% vs. 14.2%, p-value = 0.0008 – significant. The only exception is the 25–34 age group, where p = 0.149. A power analysis was conducted for this group, which showed that the current sample size (approximately 2,500 users per group) is insufficient to detect a 5% difference. The required sample size is approximately 6,279 users per group, meaning an additional 7,558 users are needed.

Outlier Analysis:
59 outliers were identified in the session_duration metric (0.59% of all data).
The distributions exhibit right-skewed asymmetry, but Welch’s t-test is robust to such deviations in large samples.

Conclusions:
The new design significantly improves user engagement:
Conversion increased by 34.6% (from 10.65% to 14.34%).
Sessions became 39.6% longer.
Users view 68% more pages.
The impact is positive for most age groups, especially for 35–44 (the highest conversion increase—5.2 percentage points).
The 25–34 age group is the only one where the change in conversion is not statistically significant. The reason is insufficient sample size, not the absence of an effect. It is recommended to collect additional data.
Outliers do not affect the reliability of the conclusions (the proportion is less than 1%).

Recommendations for business
Roll out the new design to all users—the results are compelling.
Conduct additional data collection for the 25–34 age group (approximately 6,300 users per group) to obtain a statistically significant conclusion regarding conversion.
Intensify marketing campaigns for the 35–44 segment—it responds best to the new design.
Investigate the causes of abnormally long sessions (>15 min)—these may be technical errors or highly engaged users.
Conduct a repeat A/B test 3 months after implementation to confirm the long-term effect.

## "Аналіз результатів  “Website Redesign A/B Test"

Мета проєкту:
Оцінити ефективність нового дизайну вебсторінки (варіант treatment) порівняно з поточним дизайном (варіант control). Головне питання: чи покращив новий дизайн ключові поведінкові показники користувачів, а саме:
Рівень конверсії (converted) – чи здійснив користувач цільову дію.
Тривалість сесії (session_duration) – скільки хвилин користувач провів на сайті.
Кількість переглянутих сторінок (pages_visited) – глибина перегляду.
Додатково – сегментація за віковими групами та статистичне підтвердження значущості відмінностей.

Дані:
Розмір вибірки: 10 000 користувачів
control – 5 013
treatment – 4 987
Ознаки: user_id, variant, converted, session_duration, pages_visited, age
Дані були попередньо очищені, перевірені на пропуски та викиди.

Етапи аналізу:
Підрахунок базових метрик
Кількість конверсій, середня тривалість сесії, середня кількість сторінок – окремо для кожної групи.
Статистичне тестування:
Z-тест пропорцій для конверсії.
T-тест Велча (незалежні вибірки, нерівні дисперсії) для session_duration та pages_visited.
Рівень значущості α = 0.05.

Сегментація за віком:
Групи: <25, 25-34, 35-44, 45+.
Для кожної групи повторені тести.

Аналіз викидів:
Метод міжквартильного розмаху (IQR).
Boxplot для візуалізації розподілів.
Аналіз потужності (Power Analysis)
Для групи, де конверсія виявилась незначущою (25-34), розраховано необхідний розмір вибірки.

Візуалізація:
Дашборд у Python (matplotlib) та Excel.
Графіки порівняння груп, таблиці p-value, розподіли по вікових сегментах.

За результатами аналізу, загальні показники показали, що конверсія в групі Control склала 10.65%, а в групі Treatment – 14.34%, тобто різниця становить +3.69 відсоткових пункти, що відповідає відносному зростанню на 34.6%. Середня тривалість сесії зросла з 5.03 хвилин у Control до 7.02 хвилин у Treatment, тобто +1.99 хвилини або +39.6%. Середня кількість відвіданих сторінок збільшилася з 2.98 до 5.01, різниця +2.03 сторінки, що становить відносну зміну +68.1%.

Статистичні тести підтвердили значущість цих відмінностей. Для конверсії Z-тест дав статистику z = -5.573 з p-value < 0.001, що є значущим. Тривалість сесії за T-тестом: t = -44.34, p-value < 0.001 – значуще. Кількість сторінок: t = -51.26, p-value < 0.001 – значуще. Отже, всі три метрики покращились статистично значуще.

Сегментація за віком показала, що для групи віком до 25 років конверсія в контролі 9.9%, в тесті 14.7%, p-value = 0.0053 – значуще. Для групи 25-34 років конверсія 11.3% проти 13.3%, p-value = 0.1491 – незначуще. Для групи 35-44 років: 10.3% проти 15.5%, p-value = 0.0003 – значуще. Для групи 45+ років: 10.7% проти 14.2%, p-value = 0.0008 – значуще. Єдиний виняток – група 25-34, де p = 0.149. Для цієї групи проведено Power Analysis, який показав, що поточна вибірка (близько 2500 користувачів на групу) недостатня для виявлення різниці в 5%. Необхідний розмір вибірки становить приблизно 6280 користувачів на групу, тобто потрібно ще 7558 користувачів додатково.

Аналіз викидів:
Виявлено 59 викидів у session_duration (0.59% від усіх даних).
Розподіли мають правосторонню асиметрію, але T-тест Велча є стійким до таких відхилень при великих вибірках.

Висновки:
Новий дизайн значно покращує залученість користувачів:
Конверсія зросла на 34.6% (з 10.65% до 14.34%).
Сесії стали довшими на 39.6%.
Користувачі переглядають на 68% більше сторінок.
Вплив позитивний для більшості вікових груп, особливо для 35-44 (найвищий приріст конверсії – 5.2 п.п.).
Група 25-34 – єдина, де зміна конверсії статистично не підтверджена. Причина – недостатній розмір вибірки, а не відсутність ефекту. Рекомендується дозбирати дані.
Викиди не впливають на надійність висновків (частка менша за 1%).

Рекомендації для бізнесу:
Впровадити новий дизайн для всіх користувачів – результати переконливі.
Провести додатковий збір даних для групи 25-34 (близько 6 300 користувачів на групу), щоб отримати статистично значущий висновок щодо конверсії.
Посилені маркетингові кампанії для сегменту 35-44 – він найкраще реагує на новий дизайн.
Дослідити причини аномально довгих сесій (>15 хв) – можливо, це технічні помилки або дуже залучені користувачі.
Через 3 місяці після впровадження провести повторний A/B тест для підтвердження довгострокового ефекту.
 
 ## Dashboard
 <a href="https://docs.google.com/spreadsheets/d/16e4CaLY2CjvlXSQF58kEe9qCoNhK6rQTTN8ItM4PK_c/edit?gid=981425842#gid=981425842">User  Engagement  Analysis</a>
