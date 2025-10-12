digraph HospitalAppointment {
    rankdir=TB;
    Start [shape=oval, label="Başlat"];
    Login [label="Kullanıcı Giriş Yap"];
    SelectDoctor [label="Doktor Seç"];
    SelectDate [label="Tarih ve Saat Belirle"];
    CheckAvailability [shape=diamond, label="Tarih Uygun mu?"];
    ConfirmAppointment [label="Randevu Onayla"];
    ShowWarning [label="Uyarı Mesajı Göster"];
    End [shape=oval, label="Bitir"];

    Start -> Login -> SelectDoctor -> SelectDate -> CheckAvailability;
    CheckAvailability -> ConfirmAppointment [label="Evet"];
    CheckAvailability -> ShowWarning [label="Hayır"];
    ConfirmAppointment -> End;
    ShowWarning -> End;
}

