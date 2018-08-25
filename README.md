# Class для сайта http://sms-activate.ru/
<body>
  <h4>Вся инфорация взята с офф сайта - http://sms-activate.ru/index.php?act=api</h4>
  <hr>
  <h4>1.API TOKEN - getToken()</h4>
  <p>Получаем личный TOKEN перейдя по этой ссылке http://sms-activate.ru/index.php?act=profile<br/>
  Подключаем class удобным для Вас способом. Я использую функцию "require_once 'class.php';" и объявляете токен:
  <b>_ACT_SMS::getToken( '07bd7A17ergergergegerg2f3f1cf37' ); </b> без этой строки class не будет работать!
  </p>
  <hr>
  <h4>2.Функция проверки баланса - getBalance()</h4>
  <p>Вызываем функцию таким спосбом:<b> " $balance = _ACT_SMS::getBalance(); " </b></p>
  <hr>
  <h4>3.Функция получения информации о наличии номеров - getNumbers() </h4>
  <p> Вызываем функцию таким спосбом:<b> " $getNumbers = _ACT_SMS::getNumbers($country,$operator); " </b> 
    <b>$country</b> - номер страны.<br/>
    <b>0 - Россия, 1 - Украина, 2 - Казахстан, 3 - Китай, 4 - Филиппины, 5 - Мьянма, 6 - Индонезия, 7 - Малайзия, 8 - Кения, 9 - Танзания, 10 - Вьетнам, 11 - Кыргызстан, 12 - США, 13 - Израиль, 14 - Гонконг, 15 - Польша</b> <br/>
    <b>$operator</b> - сотовый оператор.<br/> <b>Сотовый оператор номера, допустимые значения - megafon, mts, beeline,tele2,any (не обязательно, если не указано, то по умолчанию будет выдано количество в соответствии с настройкой в левом меню). ДОПУСТИМО ТОЛЬКО ДЛЯ НОМЕРОВ РФ (country=0)</b>
  </p>
  <hr>
  <h4>4. Функция получения информации о наличии номера нескольких стран сразу - getNumbersArr()</h4>
  <p>Вызываем функцию таким спосбом:<b> " $getNumbersArr = _ACT_SMS::getNumbersArr($country_arr=[],$operator=''); " </b>
    <b>$country</b> - номер страны. (указываем в массиве вот так [1,2,3,4,7,5]) <br/>
    <b>0 - Россия, 1 - Украина, 2 - Казахстан, 3 - Китай, 4 - Филиппины, 5 - Мьянма, 6 - Индонезия, 7 - Малайзия, 8 - Кения, 9 - Танзания, 10 - Вьетнам, 11 - Кыргызстан, 12 - США, 13 - Израиль, 14 - Гонконг, 15 - Польша</b> <br/>
  <b>$operator</b> - сотовый оператор.<br/> <b>Сотовый оператор номера, допустимые значения - megafon, mts, beeline,tele2,any (не обязательно, если не указано, то по умолчанию будет выдано количество в соответствии с настройкой в левом меню). ДОПУСТИМО ТОЛЬКО ДЛЯ НОМЕРОВ РФ (country=0)</b>
  </p>
  <hr>
  <h4>5. Функция заказа номера - buyNumber()</h4>
  <p>Вызываем функцию таким спосбом:<b>"$buyNumber = _ACT_SMS::buyNumber($service,$country,$operator='any',$ref='',$forward=0);" </b>
    <b>$service </b>- сервис для заказа (указаны ниже)

<b>$forward </b>- Необходимо ли выполнить переадресацию? Принимаемые значения - 0 (не выполнять), 1 - (выполнять). (необязательный параметр, по умолчанию равен 0)

<b>$operator</b> - получить номера определенного оператора (принимаемые значения: mts, tele2, megafon, beeline, any, где any - любой оператор). Необязательный параметр, по умолчанию равен any

<b>$ref</b> - передать реферальный идентификатор. Подробнее

<b>$country </b>- идентификатор страны номера (0 - Россия, 1 - Украина, 2 - Казахстан, 3 - Китай, 4 - Филиппины, 5 - Мьянма, 6 - Индонезия, 7 - Малайзия, 8 - Кения, 9 - Танзания, 10 - Вьетнам, 11 - Кыргызстан, 12 - США, 13 - Израиль, 14 - Гонконг, 15 - Польша), если не указано, то по умолчанию будет выбран номер в соответствии с указанным параметром в левом меню

<b>Список доступных сервисов:</b>

    vk(Вконтакте)
    ok(Одноклассники)
    wa(Whatsapp)
    vi(Viber)
    tg(Telegram)
    wb(WeChat)
    go(Google,youtube,Gmail)
    av(avito)
    av(avito
    +переадресация
    )
    fb(facebook)
    tw(Twitter)
    ot(Любой другой
    +переадресация
    )
    ub(Uber)
    qw(Qiwi)
    gt(Gett)
    sn(OLX)
    ig(Instagram)
    ss(SeoSprint)
    ym(Юла)
    ym(Юла
    +переадресация
    )
    ma(Mail.ru)
    mm(Microsoft)
    uk(Nike)
    me(Line messenger)
    mb(Yahoo)
    we(ДругВокруг)
    bd(OKEY)
    kp(Tencent QQ)
    dt(WOG)
    ya(Яндекс)
    ya(Яндекс
    +переадресация
    )
    mt(Steam)
    oi(Tinder)
    fd(Mamba)
    zz(Drom.ru)
    kt(KakaoTalk)
    pm(AOL)
    tn(LinkedIN)
    ot(Любой другой)
  </p>
  <h4>6. Функция получения статуса о заказе номера - getStatus()</h4>
  <p>Вызываем функцию таким спосбом:<b>"$getStatus = _ACT_SMS::getStatus($id);" </b> 
  <b>$id</b> - номер заказа.
  
  </p>
</body>
