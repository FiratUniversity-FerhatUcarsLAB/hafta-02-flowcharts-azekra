digraph ShoppingCart {
    rankdir=TB;
    Start [shape=oval, label="Başlat"];
    SelectProduct [label="Ürün Seç"];
    AddToCart [label="Sepete Ekle"];
    GoToPayment [label="Ödeme Sayfasına Git"];
    EnterPayment [label="Ödeme Bilgilerini Gir"];
    CheckPayment [shape=diamond, label="Ödeme Başarılı mı?"];
    ConfirmOrder [label="Siparişi Onayla"];
    ShowError [label="Hata Mesajı Göster"];
    End [shape=oval, label="Bitir"];

    Start -> SelectProduct -> AddToCart -> GoToPayment -> EnterPayment -> CheckPayment;
    CheckPayment -> ConfirmOrder [label="Evet"];
    CheckPayment -> ShowError [label="Hayır"];
    ConfirmOrder -> End;
    ShowError -> End;
}
