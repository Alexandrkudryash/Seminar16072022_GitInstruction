# **Домашнее задание от Семинара-2 (от 11.07.2022) к предмету Контроль версий** _с дополнением к Семинару от 16.07.2022_.

Студент: **_Кудряшов Александр_**

## Дополненная версия от 16.07.2022 г.:

Работа на Семинаре-16-07-2022, завершение работы с файлом после окончания семинара
в качестве домашнего задания.

Дата подготовки: 23.07.2022 (т.к. срок 5 дней нарушен (Каникулы ведь! 18-31 июля), послал запрос на продление срока, платформа ГикБрейнс подтвердила продление до 06.08.2022).

Цель домашнего задания:

* Учимся работать с удалённым репозиторием.
* Доработать файл, внести изменения, отправить локальные изменения на удалённый репозиторий.
* 


## Старая версия от 14.07.2022 г.
Дата и время выполнения домашнего задания: 14.07.2022 11:00.

**Цель Домашнего задания**: 
* завершить подготовку инструкции по работе с Git
* выполнить несколько слияний веток
* создать ситуацию хотя бы одного конфликта при слиянии веток
* дописать про все команды Git, которые мне известны


# Инструкция по работе с Git и удаленными репозиториями


## Что такое Git?

Git - это одна из реализаций распределенных систем контроля версий, что позволяет иметь версионность как в локальном репозитории, так и в удалённом репозитории (общем для всех). Git 
является на данный момент самой популярной системой контроля версий.

## Подготовка репозитория
Для создания репозитория используется команда "git init". В терминале в папке с будущим репозиторием достаточно написать "git init", и эта папка станет репозиторием.


## Просмотр сделанных изменений
Для того чтобы просмотреть разницу между текущей версией файла и версией файла в последнем коммите, используется команда *git diff*. Для этого в терминале с папкой с репозиторием, напишите *git diff*

## Создание нового Коммита

Создание комитов - это одна из основных задач программы Git -  периодически выполняя сохранения рабочего материала (редактируемого файла, программного кода), с помощью команды Ctr+S в редакторе VisualStudio Code и затем выполняя две команды Git (git add filename и git commit -m "Commit message"), мы можем сохранять различные стадии/версии результатов нашей работы. Сообщение "Commit message", указываемое во второй команде - это информация, которая позволяет видеть какое именно изменение мы вносили на определённой стадии/версии нашего рабочего файла, и, при необходимости, по этому комментарию мы можем найти эту версию и "откатиться" к ней".


## Состояние репозитория
Для того, чтобы посмотреть состояние репозитория, используется команда "git  status". Для этого в терминале с папкой-репозиторием необохоимо напписать "git status", и возможно увидеть несколько состояний:
1. Nothing to commit - репозиторий не содержит изменений
2. Unversioned file - папка содержит файл, к которому не добавлена версионность.



### Просмотр состояния репозиториев


Для просомтра состояния репозитория используется команда *git status*.  Для этого необоходимо в папке с терминалом написать *git status*, и увидеть несколько возможных состояний:
1. Nothing to commit - это значит, что в репозитории нет абсолютно никаких изменений.
2. Universioned file - означает, что файл не отслеживается программой Git.


### Добавление файла в коммит

Для добавления файла в текущий коммит используется команда "git add". Для этого достаточно в терминале с папкой текущего репозитория написать *git add <название файла>*.

### Сохранение коммита
Для сохранения коммита используется команда "git commit". Для этого в терминале с папкой репозитория необходимо написать команду *git commit -m "<соообщение коммиту>"*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.


## Журнал изменений
Для просмотра истории коммитов, то есть истории наших изменений используется команда *git log*. Для этого необходимо в терминалес папкой репозитория написать *git log*. 

## Перемещение между "сохранениями"

Для того, чтобы перемещаться между коммитами, необходимо использовать команду "git checkout". Для этого в терминале с папкой репозитория необходимо написать *git checkout <номер коммита>*. Номер коммита берётся из истории изменений. После такого "перемещения" мы попадаем в состояние **Detached head*. Для возвращения в обычное состояние используется команда *git checkout master*.

## Ветки в Git
В программе Git есть возможность создания дополнительных версий рабочего файла, так называемых "веток". Обозначение "ветка" очень точно отображает суть формата создаваемой дополнительной версии файла, т.к. осноная версия файла не меняется в момент создания и развития новой версии или "ветки". Это также удобно для групповой работы в одном рабочем файле, когда можно отследить действия автора новой ветки, и иметь возможность согласовать новую версию с лидером (хозяином) основной редакции файла.

Для создания новой ветки необходимо выполнить команду <git branch>, чтобы увидеть какие вообще ветки редактируемого файла существуют в данный момент.

Данная команда отобразит список уже созданных веток, а также сообщит пользователю в какой ветке он находится. 

Создание новой ветки выполняется командой "*git branch NewBranchName*", где "NewBranchName" - это произвольное наименование вновь создаваемой ветки. При создании новой ветки, в её содержимое войдет полная копия ветки, в которой находится пользователь в момент создания новой ветки (по умолчанию это скорее всего ветка Master, но не обязательно).

После создания новой ветки необходим в неё переместиться с помощью команды "*git checkout NewBranchName*", и проверить командами "*git branch*", "*git status*", действительно ли пользователь туда переместился.

Далее пользователь может спокойно выполнять редактирование новой ветки, и выполнять коммиты, с целью сохранения всех этапов выполняемой работы.


## Слияние веток и решение конфликтов

При завершении работы в отдельной ветке и наличии полной уверенности в готовности подготовленных доработок для включения их в основную ветку рабочей версии файла, необходимо выполнить команду слияния - т.е. "залить" данные, созданные в этой ветке в основную (т.е. в ветку master).

Слияние запускается следующей командой: "*git merge BranchName*", где BranchName - это наименование ветки, данные которой необходимо "залить" в ветку master.
Очень важно, перед запуском команды - перейти в ветку master, и после перехода - нужно убедиться, что этот переход состоялся с помощью команд "*git branch*", "*git status*".
Команда "*git merge*" выполняет перенос данных в ту ветку, в которой находится пользователь из той ветки, которая указана в команде слияния, т.е. BranchName.

Бывают ситуации, когда в процесе слияния информация, "заливаемая" в текущую ветку отличается от имеющейся информации в текущей ветки. Это создаёт конфликт, т.к. функция слияния расчитана за закачку новой информации. При закачке подобных данных, но имеющих отличия, программа git видит эти различия, и отображает на экране ситуацию конфликта - т.е. наличия двух версий одного и того же текста (это не отностися к новой части текста). В этом случае программа Git предлагает пользователю несколько вариантов действий - обе, конфликтующие между собой версии текста заключаются в особые знаки (знаки "равно" ===== и текст HEAD в верхнеей части выделенного текста обеих версий), над этими, выделенными частями появляется меню из нескольких опций, одну из которых можно выбрать кликнув мышкой: 
* принять текущие данные но не принимать закачиваемые данные
* принять новые данные и удалить текущие данные
* принять обе версии текста
* сравнить версии текста.

Наиболее оптимальным вариантом является ручное решение конфликта: вручную отредактировать текст, оставив ту редакцию, которая по мнению пользователя должна остаться в итоге, и вручную удалить ненужный текст, а также необходимо удалить новые символы, выделяющие возникшую зону конфликта в тексте. После выполнения указанных изменений текста - выполнить сохранение командой Сtrl+S, затем выполнить коммит, где указываем, что завершили слияние с определенной веткой.


## Удаление веток   

После завершения слияния ветки master и BranchName (т.е. какой-то дополнительной ветки), ветка BranchName становится ненужной, её можно (и нужно) удалить. 

Выполняется это с помощью команды: "*git brancn -d BranchName*".

## Отправка изменений в GitHub

Для отправки изменений в удаленный репозиторий необходимо использовать команду git push. Для этого  в терминале с папкой с репозиторием связанной с удаленным репозиторием пишем команду git push origin название ветки,
где название ветки  - это ветка в удаленном репозитории куда необходимо отправить совершенные изменения.

## Скачивание изменений с удаленного репозитория
  
  Для того, чтобы скачать изменения с удаленного репозитория, необходимо использовать команду git pull.
  в терминале с папкой репозитория, связанным с уаденным репозиторием пишем git pull ogitin название ветки для того чтобы принять измнеенния  из указанной ветки удаленного репозитория

  
  
