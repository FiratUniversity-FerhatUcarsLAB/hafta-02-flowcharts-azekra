digraph ATM {
    rankdir=LR;
    node [shape=rectangle, style=rounded, fontsize=12];

    Start [label="Başla"];
    InsertCard [label="Kartı Tak"];
    EnterPIN [label="PIN Gir"];
    CheckPIN [shape=diamond, label="PIN Doğru mu?"];
    SelectTransaction [label="İşlem Türünü Seç (Para Çekme)"];
    EnterAmount [label="Miktarı Gir"];
    CheckBalance [shape=diamond, label="Bakiye Yeterli mi?"];
    DispenseCash [label="Parayı Ver ve Bakiyeyi Güncelle"];
    PrintReceipt [shape=diamond, label="Fiş İstiyor musun?"];
    Receipt [label="Fişi Yazdır"];
    EjectCard [label="Kartı Çıkar"];
    End [label="Bitir"];
    ErrorPIN [label="Yanlış PIN"];
    Insufficient [label="Yetersiz Bakiye"];

    Start -> InsertCard -> EnterPIN -> CheckPIN;
    CheckPIN -> SelectTransaction [label="Evet"];
    CheckPIN -> ErrorPIN [label="Hayır"];
    ErrorPIN -> EnterPIN;

    SelectTransaction -> EnterAmount -> CheckBalance;
    CheckBalance -> DispenseCash [label="Evet"];
    CheckBalance -> Insufficient [label="Hayır"];
    Insufficient -> EnterAmount;

    DispenseCash -> PrintReceipt;
    PrintReceipt -> Receipt [label="Evet"];
    PrintReceipt -> EjectCard [label="Hayır"];
    Receipt -> EjectCard -> End;

}
