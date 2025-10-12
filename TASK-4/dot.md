digraph CourseRegistration {
    rankdir=TB;
    node [shape=box, style=filled, color=lightblue];

    Start [shape=oval, label="Başlat"];
    Login [label="Öğrenci Giriş Yap"];
    CheckLogin [shape=diamond, label="Giriş Başarılı mı?"];
    GetSemester [label="Dönem Bilgisi Al"];
    ShowCourses [label="Ders Listesi Göster"];
    SelectCourses [label="Dersleri Seç"];
    CheckConflict [shape=diamond, label="Dersler Çakışıyor mu?"];
    CalculateCredits [label="Toplam Kredi Hesapla"];
    CheckCredits [shape=diamond, label="Kredi Limiti Aşıldı mı?"];
    ConfirmRegistration [label="Kayıt Tamamlandı"];
    ShowConflictWarning [label="Ders Çakışma Uyarısı"];
    ShowCreditWarning [label="Kredi Limiti Uyarısı"];
    ShowLoginError [label="Giriş Hatası"];
    End [shape=oval, label="Bitir"];

    Start -> Login -> CheckLogin;
    CheckLogin -> GetSemester [label="Evet"];
    CheckLogin -> ShowLoginError [label="Hayır"];
    GetSemester -> ShowCourses -> SelectCourses -> CheckConflict;
    CheckConflict -> CalculateCredits [label="Hayır"];
    CheckConflict -> ShowConflictWarning [label="Evet"];
    CalculateCredits -> CheckCredits;
    CheckCredits -> ConfirmRegistration [label="Hayır"];
    CheckCredits -> ShowCreditWarning [label="Evet"];
    ConfirmRegistration -> End;
    ShowConflictWarning -> End;
    ShowCreditWarning -> End;
    ShowLoginError -> End;
}
