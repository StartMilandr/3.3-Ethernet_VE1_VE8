﻿# Ethernet_VE1_VE8

Проверка обмена по Ethernet при подключении микроконтроллеров 1986ВЕ1Т и 1986ВЕ8Т.

В тесте передаются пакеты с постоянно увеличивающейся длиной. Кнопками на старте выбирается режим работы буферов - линейный, автоматический или FIFO. Во всех режимах обмен происходит успешно, ошибки не фиксируются.

Необходимо использовать Cross кабель.

Инициатором обмена может являться любой МК, это определяется макроопределением

  #define IS_STARTER

В случае когда 1986ВЕ8Т запускает обмен, требуется вторичная посылка первого пакета. По какой-то причине первый пакет не фиксируется приемником 1986ВЕ1Т. Возможно он теряется при синхронизации блоков PHY, то есть блоки на момент старта не синхронизированы.

При запуске старта от 1986ВЕ1Т обмен стартует с первого же фрейма. Вероятно 1986ВЕ генерирует линк сигнал и блоки на момент старта синхронизированы.

Проект является продолжением проекта и статьи по проверке блоков Ethernet в режиме КЗ 
  - https://github.com/StartMilandr/Tests/tree/master/Eth_TestLengthLB
  - https://startmilandr.ru/doku.php/prog:ethernet:test_cl