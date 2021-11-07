# Repeater
HTTP通信の再送、および、改変を行える機能。  

Proxyタブ内のHTTP Historyタブで、対象となる通信を右クリックし「Send to Repeater」で取り込める。  
ショートカットはCtrl＋R（**R**epeaterの**R**）。

取り込まれたHTTPリクエストを「Pretty」または「Raw」タブから直接編集することが可能。

Request Attributesから指定することでHTTP/1.1とHTTP/2の切り替えができる。

同じ通信を繰り返すだけの機能のため、エラー発生時にセッションが破棄される場合などは途中で使用できなくなる。
