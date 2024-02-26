### Именование ветвей и тегов
При использовании CLI могут возникнуть ситуации, когда имя ветки или тега содержит специальные символы, имеющие особое значение для вашей среды оболочки. Чтобы безопасно использовать эти символы в команде Git, они должны быть заключены в кавычки или экранированы, иначе команда может иметь непредвиденные последствия.

Например, этот ```$``` символ используется во многих оболочках для ссылки на переменную. Большинство оболочек интерпретируют допустимое имя ветки как ```hello-$USER``` эквивалент слова «привет», за которым следует дефис, за которым следует текущее значение переменной ```USER```, а не буквальная строка ```hello-$USER```. Если имя ветки включает этот ```$``` символ, то оболочке необходимо запретить расширять его как ссылку на переменную. Аналогично, если имя ветки содержит точку с запятой (```;```), большинство оболочек интерпретируют ее как разделитель команд, поэтому ее необходимо заключить в кавычки или экранировать.

#### Экранирование специальных символов в именах ветвей и тегов
Большинство имен ветвей и тегов со специальными символами можно обрабатывать, заключая имя в одинарные кавычки, например ```'hello-$USER'```.

- В оболочке Bash заключение строки символов в одинарные кавычки сохраняет буквальное значение символов в одинарных кавычках.
- Zsh ведет себя аналогично Bash, однако это поведение можно настроить с помощью этой RC_QUOTESопции.
- PowerShell также воспринимает символы буквально, если они заключены в одинарные кавычки.

Для этих оболочек основным исключением является ситуация, когда имя ветки или тега содержит одинарную кавычку. В этом случае вам следует обратиться к официальной документации вашей оболочки:
- Документация [Bash] (https://www.gnu.org/software/bash/manual/)
- Документация [Zsh] (https://zsh.sourceforge.io/Doc/)
- Документация [Fish] (https://fishshell.com/docs/current/)
- Документация [PowerShell] (https://learn.microsoft.com/en-gb/powershell/)

### Именование ветвей и тегов
Если возможно, создавайте имена ветвей и тегов, не содержащие специальных символов, поскольку их необходимо будет экранировать. Безопасный набор символов по умолчанию, используемый для имен ветвей и имен тегов:
1. Английский алфавит (```a``` до ```z``` и ```A``` до ```Z```)
2. Числа (```0``` до ```9```)
3. Ограниченный набор знаков препинания:
    - период (```.```)
    - дефис (```-```)
    - нижнее подчеркивание (```_```)
    - косая черта (```/```)
Чтобы избежать путаницы, названия ветвей следует начинать с буквы.

### Ограничения на имена в GitHub
GitHub ограничивает отправку небольшого количества имен ветвей и тегов. Эти ограничения таковы:
- Никаких имен, похожих на идентификаторы объектов Git (40 символов, содержащих только 0–9 и AF), чтобы избежать путаницы с фактическими идентификаторами объектов Git.
- Никаких имен, начинающихся с ```refs/```, чтобы избежать путаницы с полным именем ссылок Git. Дополнительную информацию о ссылках см. в разделе [«Ссылки на Git»](https://git-scm.com/book/en/v2/Git-Internals-Git-References) документации Git.