@startuml
left to right direction

actor "Шкипер" as Skipper
actor "Ковальски" as Kowalski
actor "Рико" as Rico
actor "Младший" as Private
actor "Охрана" as Guard

package "Побег из зоопарка" {
    usecase "Взломать замок" as Hack
    usecase "Захватить судно" as CaptureShip
    usecase "Уплыть в Антарктиду" as Sail
    usecase "Усыпить охрану" as Sleep
    usecase "Отвлечь внимание" as Distract
}

' Шкипер управляет захватом судна
Skipper --> CaptureShip

' Ковальски взламывает
Kowalski --> Hack

' Рико усыпляет охрану
Rico --> Sleep

' Младший отвлекает
Private --> Distract

' Зависимости внутри системы
CaptureShip .> Hack : <<include>>
CaptureShip .> Sleep : <<include>>
CaptureShip .> Distract : <<include>>
Sail ..> CaptureShip : <<extend>>

@enduml
