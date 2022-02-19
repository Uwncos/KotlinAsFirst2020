Сделан форк KotlinAsFirst2020
Проект KotlinAsFirst2020 добавлен в IDEA
Пишу:
 $ git remote
смотрим список подключений к репозиториям
Указываю в качестве upstream-my свой форк по ссылке (https://github.com/Uwncos/KotlinAsFirst2021.git):
 $ git remote add upstream-my "https://github.com/Uwncos/KotlinAsFirst2021.git"
смотрим список, всё добавилось:
 $ git remote -v
Пишу:
 $ git pull upstream-my
Получилось (done)
Не указал branch (You asked to pull from the remote 'upstream-my', but did not specify
a branch. Because this is not the default configured remote
for your current branch, you must specify a branch on the command line.)
Смотрю граф, ничего и не появилось.
Пишу:
 $ git merge upstream-my/master
 $ gitk (- все есть).
Создаю ветку backport.
С помощью cherry-pick переношу туда мои решения задач:
 $ git cherry-pick 1137b420cc95fa6894edad69b31e2da1bb985d1d..f62799393f1b393c427b5f7fec6c6d362e0075cc
Теперь добавляю upstream-theirs:
 $ git remote add upstream-theirs "https://github.com/goitart/KotlinAsFirst2021.git"
Смотрю remote -v
И делаю fetch upstream-theirs
Делаю merge:
 $ git merge -s ours upstream-theirs/master 
Merge made by the 'ours' strategy. (т.е все конфликты разрешаются в мою сторону)
Пишу:
 $ git remote -v
вставляю вывод в txt файл и кладу в папку проекта. Делаю commit с комментарием "remotes".
Проверяю граф, все на месте, в комментарии к коммиту "remotes" лежит файл remotes.txt
Делаю коммит с этим файлом (howto.dm) по аналогии.