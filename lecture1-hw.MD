### 1. Создать репозиторий в GitHub
### 2. Установить Virtualbox, установить Ubuntu.
### 3. Установить утилиты для гостевой ОС вручную и написать команды для
-- установка недостоющих зависимостей gcc make perl
### 4. В конфигурации виртуальной машины включить "общий буфер". На macOS заменить NAT сетевой интерфейс на Bridged . На Windows добавить еще один internal интерфейс.
### 5. Настроить ssh соединение с хостовой ОС на гостевую ОС с использованием ssh ключа и написать команды для:
-- установки ssh сервер
-- добавления порта 22 в исключения фаервола ufw (самостоятельно найти)
-- генерации ssh ключа
### 6. * https://github.com/mtuktarov/linux_stuff/blob/master/lecture1-hw.MD

Примечание. Задания 6 дано для тех, кому упражнений 1-5  показалось недостаточно.



### Урок 1. Дополнительные задания
1. Ты случайно обнаружил, что пользователь **root** подключиться по ssh не может. Надо разобраться, и сделать так, чтобы пользователь **root** мог подключаться по ssh к машине с Ubuntu.

2. Представим, что ты делишь свою компьютер с другими ребятами, которые плохо знают Linux. Они подключаются к твоей машине по ssh, причем используют Терминал другой unix машины или Putty, не вводя пароль в настройках. Уже пятый раз тебе звонят и спрашивают, почему при вводе пароля символы не печатаются. Тебе это надоело и ты хочешь сделать так, чтобы **при подключении по ssh** **ДО ввода пароля** пользователю выводилось сообщение о том, что символы, которые он вводит не будут отображаться:

```

********************************************************************
*                        <<< WARNING >>>                           *
*==================================================================*
* This ubuntu machine is solely for the use of authorized users.   *
* Hopefully, you know what you're up to. Just remember:            *
*                                                                  *
*      Do not allow children to play in the dishwasher!!!          *
*                                                                  *
* Oh, sorry... I meant be aware:                                   *
*                                                                  *
*        You will not see symbols while typing your password.      *
*  That's ok - they are still typed. We care about your security.  *
********************************************************************

```

- А теперь сделай так, чтобы для всех пользователей это сообщение выводилось, а для пользователя **root** это сообщение не выводилось.

3. Все в Ubuntu хорошо, да вот столько фигни всякой показывает она при подключении по ssh! Нужно бы разобраться, как сделать так, чтобы после подключения по ssh показывались ТОЛЬКО сообщения о дистрибутиве/ядре, состоянии пакетов и Last login. Например:

```
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 5.0.0-23-generic x86_64)

240 packages can be updated.
142 updates are security updates.

Last login: Fri Dec 13 04:40:07 2019 from 127.0.0.1
```

- А теперь сделай так, чтобы для всех пользователей эти сообщения показывались, кроме пользователя **root**.

#### Помнить нужно только самое важное
4. Очень часто бывают ситуации, когда ты не помнишь какую-то информацию о пакете, который тебе нужно установить. При этом доступа в интернет нет. Круто, что достаточно помнить пару команд, чтобы найти информацию о любом пакете. В этом я и предлагаю разобраться.

- представим, что тебе нужно установить два пакета, а ты не помнишь их названия. Но зато точно помнишь что в одном из этих пакетов был файл с названием **landscape-sysinfo**, а в другом пакете - файл с названием **ansiweather**. Нужно разобраться, как узнать имя пакета, зная имя файла, который в нем находится.

- после этого ты вспоминаешь, что тебе нельзя не при каком условии устанавливать пакеты, в которых есть файл **/usr/bin/virus**. Ты решаешь убедиться что в этих пакетах таких файлов нет. Нужно разобраться, как показать файлы, которые содержатся в пакете, зная его имя, но при этом не устанавливая его.

- разобравшись с названиями пакетов и их содержимом, ты внезапно понял, что понятия не имеешь, что это за пакеты. Нужно разобраться, как показать полную информацию о пакете, чтобы было понятно, для чего он нужен.
- После этого установи пакеты. Обрати внимание, что теперь при подключении по ssh появилась новая информация.

5. Используя скрипт из установленного пакета, сделай так, чтобы при подключении показывалась информация о погоде в твоем городе. Используй **man** для получения дополнительной информации об использовании скриптов. Должно получиться что-то вроде:

```
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 5.0.0-23-generic x86_64)

  System load:  0.0                Processes:             248
  Usage of /:   11.6% of 62.74GB   Users logged in:       1
  Memory usage: 51%                IP address for enp0s5: 10.211.55.6
  Swap usage:   0%

 Weather in Moscow => 2 °C - Wind => 4 m/s S - Humidity => 74 % - Pressure => 1018 hPa

240 packages can be updated.
142 updates are security updates.

Last login: Fri Dec 13 05:00:22 2019 from 127.0.0.1
```

6. Теперь тебя уже не остановить! Почему бы не сделать так, чтобы эта информация показывалась не только при подключении по ssh, но и когда открываешь Терминал локально...

