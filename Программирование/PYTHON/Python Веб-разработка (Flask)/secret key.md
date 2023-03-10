Типичный способ защиты сайтов – это «секретный ключ» (secret), специальное значение, которое генерируется случайным образом и сохраняется в сессии посетителя. Его знает только сервер, посетителю мы его даже не будем показывать.

Затем на основе ключа генерируется «токен» (token). Токен делается так, чтобы с одной стороны он был отличен от ключа, в частности, может быть много токенов для одного ключа, с другой – чтобы было легко проверить по токену, сгенерирован ли он на основе данного ключа или нет.

Для каждого токена нужно дополнительное случайное значение, которое называют «соль» salt.

Формула вычисления токена:

token = salt + ":" + MD5(salt + ":" + secret) Например:

В сессии хранится secret="abcdef", это значение создаётся один раз. Для нового токена сгенерируем salt, например пусть salt="1234". token = "1234" + ":" + MD5("1234" + ":" + "abcdef") = "1234:5ad02792a3285252e524ccadeeda3401". Это значение – с одной стороны, случайное, с другой – имея такой token, мы можем взять его первую часть 1234 в качестве salt и, зная secret, проверить по формуле, верно ли он вычислен.

Не зная secret, невозможно сгенерировать token, который сервер воспримет как правильный.

Далее, токен добавляется в качестве скрытого поля к каждой форме, генерируемой на сервере.При её отправке сервер проверит поле csrf, удостоверится в правильности токена, и лишь после этого отошлёт сообщение.

«Злая страница» при всём желании не сможет сгенерировать подобную форму, так как не владеет secret, и токен будет неверным.