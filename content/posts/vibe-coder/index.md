---
title: "vibe coder"
date: 2026-01-14T10:00:00+01:00
draft: false
tags: ["AI", "Home Assistant", "kubernetes", "k8s", "homeassistant-operator"]
---

## Wydałem kasę na AI i teraz muszę to jakoś usprawiedliwić

Zdecydowałem się, a co mi szkodzi. Już sobie z ciekawości kupiłem subskrypcje na LLMy i inne brajry to czemu by jej nie wykorzystać? Po używałem tochę i ma to potencjał, nie mam dużego doświatczenia jako coder wiec dla mnie to imponujace. Zastanawiałem się dłuższy czas gdzie moge to wykorzytać. Zawsze chciałem poświęcić trochę czasu na Open Source tylko nigdy tego czasu nie miałem dostecznie dużo by dać wartościowy wkład ale z takim narzędziem? Podstawowe bugi nie powinny być problemem, jest tyle rzeczy do poprawienia na GitHub i dużo z nich to są "low hanging fruit" wiec czemu by coś nie po commitować i trochę się pobawić?

![ah AI](boy.jpg)


## Wizja wielkiego dzieła, które pewnie mnie przerośnie

Ale naszła mnie pewna myśl może by zrobić coś od zera zupełnie samemu, miec coś tak swojego że ma się wpływ na wszystko, pełną kontrole, mnustow decyzji projektowych do podjecia. Tak ta myśl była pociągająca tylko nie miałem tego czegoś. Chciałem też żeby to miało znaczenie dla mnie czy dla innch bo może uda mi się coś osiągnąć. No właśnie to też powinno być coś ambitego, bo ciekawi mnie do czego ten Vibe mnie zaprowadzi, czy naprawde jest uzyteczny, a moze aplikacje które są bardziej skąplikowane niż proste parsery czy narzedzia CLI rozsypią sie po 8 commicie ?

![przecież to proste](doom.jpg)

## Home Assistant: bo zwykłe życie było zbyt stabilne

A jekie są moje zainteresowania? Nie chce też stracić zainteresowania projektem po 3 tygodniach. Od jakiegoś czasu automatyzuje sobie codzienne czynności za pomocą Home Assistant, swiatła same się włączają o określonych godzinach na podwórzu, lodówka jak jest za długo otwarta wyła powiadomieni na telefon, światła w pokoju gasną gdy włączam kosole do grania. Niby nic ale trochę czasu na to idzie, a to jakiś czujnik w domu się nie łaczy do sieci, a to skrypt nie pokrywa wszystkich moich nawyków - fajna zabawa trochę software engineering tochę hardware nudy nie ma. No i tesknie za kubernetesem, oj to będzie już z 9 miesięcy gdy nic tak na poważnie nie grzebnałem przy podach, nie edytowałem CRD albo debugoweałem rozproszonych systemów. W zeszłym roku miałem nawet podjeście do tego żeby Home Assistant uruchomic w k8s - łatwo nie było projekt Home Assistant nie supportuje takiego sposobu instalacji, ma kontenery ale domyślnym sposobem jest uruchomienie tego w dockerze. Jest też wersja Home Assistant Operating System która jest zasadniczo instlacją gdzie wszystkie jego części są uruchamiane w kontenerach dodatkowo są zautomatyzowane instalacje pluginów które są niczym innym jak kontenerami z predefinowana cofigguracją. Udało mi się zainslować całość na k8s, mnustow yamli i debugowania czemu moje manifesty nie współgają ze sobą ze 2 tygodnie zabawy z mizernym efektem - działało ale nie stabilnie, głownie dlatego że to było moje pierwsze podejscie do HA i nie byłem świadomy do końca jego archtekury oraz jak całość ma właściwie współgrać.

![No udało się](kid.jpg)

## GitOps albo śmierć - Projekt, którego nikt nie potrzebował

A gdyby to wszytko połączyć? Strasznie irytowało mnie w HA że wszystko w nim trzeba wyklikiwać, co prawda można skrypty pisać w yamlu ale nie można robić to we własnym IDE a już o GitOps nie ma mowy. Może obejść te wszytkie problemy. Społeczność sama z siebie nie stowrzy żdnego suporotwanego sposobu na uruchomienie HA w k8s nie to jest ich celem a użytkownicy którzy z tego by korzystali na codzień pewnie mieszczą się w jednej sali kinowej. To jest idealny pomysł! Napisze własnego operatora! Masa CRD i automatyzacji, zmuszanie systemów które nie były pod to projektowane do przeskakiwnia między nodami, może nawet storze wesje HA HA :)

![Czy to Iron Man?](fine.jpg)

## Gdy Geniusz Przemawia, YAML Milknie

Postanowione [homeassistant-operator](https://github.com/przemekhys/homeassistant-operator) zostanie powołany do życia! Będzie napędzany marzeniami, kawą i AI. Będzie to nie samowity test gdzie można zajechać nie będąc doświatczonym prgramistą, znając podstawy GO, o k8s sie nie martwie raczje jestm tu biegły. Cel - nauczyć sie jak najwiecej, pewnie będę sam pchał ten projekt jak dalego się da sam jestem ciekaw w którym momęcie pody będą sie randomow restartował. 

![Hold My Beer, bez alkocholowe](beer.jpg)