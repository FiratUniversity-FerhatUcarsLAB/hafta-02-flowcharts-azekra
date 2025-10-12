digraph SmartHomeSecurity {
    rankdir=TB;
    node [shape=box, style=filled, color=lightgrey];

    Start [shape=oval, label="Başlat"];
    ActivateSystem [label="Sistemi Aktif Et"];
    SelectMode [label="Gece/Gündüz Modu Seç"];
    MonitorSensors [label="Sensörleri İzle"];
    MotionDetected [shape=diamond, label="Hareket Algılandı mı?"];
    TriggerAlarm [label="Alarm Çal"];
    SendNotification [label="Bildirim Gönder"];
    ContinueMonitoring [label="İzlemeye Devam Et"];
    DeactivateSystem [shape=diamond, label="Sistem Devre Dışı mı?"];
    StopMonitoring [label="İzleme Durdur"];
    End [shape=oval, label="Bitir"];

    Start -> ActivateSystem -> SelectMode -> MonitorSensors -> MotionDetected;
    MotionDetected -> TriggerAlarm [label="Evet"];
    TriggerAlarm -> SendNotification -> ContinueMonitoring;
    MotionDetected -> ContinueMonitoring [label="Hayır"];
    ContinueMonitoring -> DeactivateSystem;
    DeactivateSystem -> StopMonitoring [label="Evet"];
    DeactivateSystem -> MonitorSensors [label="Hayır"];
    StopMonitoring -> End;
}
