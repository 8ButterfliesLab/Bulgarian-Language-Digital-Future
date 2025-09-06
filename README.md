# Bulgarian-Language-Digital-Future
Manifesto + tools for digital support of the Bulgarian language
🇧🇬 Българският в дигиталния свят — общностен корпус и инструменти
Мисия

Да направим българския пълноправен дигитален език: да има качествени речници, корпуси, TTS/STT гласове и отворени инструменти, с които всеки може да пише, чете и създава на български — в училище, медии, наука, бизнес и изкуство.

Как да се включиш (бърз старт)

🌟 Писатели/читатели: дари текстове или разреши използване на твои публикации.

🎤 Доброволци за говор: запиши кратки изречения (TTS/STT колекции).

🧑‍💻 Разработчици/лингвисти: прегледай задачи в Issues и подай PR.

🏛 Институции/НПО/медии: свържете се за меморандуми за данни и съвместни проекти.

Структура на репото
/docs            – манифест, етика, инструкции
/data
  /text          – .txt/.jsonl корпуси (+метаданни)
  /audio         – .wav/.flac записи (+transcript.jsonl)
  /lexicon       – речникови списъци, морфология
/tools           – скриптове за нормализация/валидация
/models          – експерименти (notebooks, configs)
CONTRIBUTING.md  – как да допринасяме
CODE_OF_CONDUCT.md
LICENSE

Етика и съгласие

Само доброволни дарения на данни с изрично съгласие.

Премахване по искане на участник във всеки момент.

Анонимизация по подразбиране (освен ако дарителят изрично поиска атрибуция).

Данните се използват само за езикови технологии на български и се публикуват с отворени лицензи.

Пример за съгласие (текст)

Давам съгласие текстът ми „___“ да бъде включен в отворен корпус за български език, публикуван под CC BY-SA 4.0 (или CC0). Разбирам, че мога да оттегля съгласието си с имейл до ___.

Пример за съгласие (аудио)

Давам съгласие моите гласови записи да бъдат публикувани за изследователски и образователни цели под CC BY 4.0 (или CC0), включително за обучение на TTS/STT модели. Мога да поискам изтриване по всяко време.

Формати на данни

Текст (JSONL):

{"id":"doc_0001","source":"donation","title":"...", "author":"anon", "year":2023,
 "license":"CC-BY-SA-4.0","text":"..."}


Аудио (WAV + transcript.jsonl):

{"utt_id":"spk01_0001","speaker":"anon","gender":"unspecified",
 "sampling_rate":16000,"license":"CC0",
 "path":"audio/spk01_0001.wav","text":"Здравей, свят!"}

Качество (минимум)

Текст: UTF-8, без сканирани артефакти; правописна норма 2012+; без дубликати.

Аудио: 16kHz/16-bit mono WAV, <10% шум; четене естествено, не „декламирано“.

Транскрипции: точно следване на казаното; пунктуация по БДС.

Инструменти (минимален пакет)

tools/normalize_text.py – унифицира кавички/тирета, премахва HTML.

tools/deduplicate.py – MinHash дубликат детектор.

tools/vad_split.py – автоматично рязане на аудио по тишина.

tools/validate_corpus.py – проверка на лиценз/метаданни.

Лицензиране

Код: Apache-2.0

Корпуси: CC BY-SA 4.0 (или CC0 за максимална свобода, ако дарителят избере CC0)

Пътна карта (v0 → v1)

 v0.1: 5M+ думи модерен текстов корпус; 5ч разнообразно аудио

 v0.2: Морфологичен анализатор (lemma+POS), базов spell-check

 v0.3: STT baseline (Whisper fine-tune) и TTS baseline (VITS/Glow-TTS)

 v1.0: Публични модели + плъгини за MS Office / LibreOffice / Docs

Как да допринеса?

Fork → feature branch → PR

Подпис на Contributor License Agreement (CLA) (автоматично при PR).

Спазвай CODE_OF_CONDUCT.

За файлове >50MB – използвай Git LFS.

Контакт

Имейл на поддръжката: bulgarian-language@abv.bg

Канал за координация: Discord/Matrix (линк в docs/COMMUNITY.md)

🇬🇧 Bulgarian in the Digital World — community corpus & tools

(Short English mirror so international contributors can join.)
Mission: Open corpora, lexicons, and speech data for Bulgarian; baseline STT/TTS; practical plugins for writers, students, and institutions.

Contribute: donate texts, record speech, review data, or open PRs.
Ethics: explicit consent, revocable at any time; default anonymization; open licenses only.
Data formats: JSONL for text; WAV+JSONL for speech (16k/16-bit mono).
Roadmap: v0 corpora → morph analyzer & spell-check → STT/TTS baselines → writer plugins.
License: Code Apache-2.0; Data CC BY-SA 4.0 (or CC0 if chosen by donors).

Issues 

good first issue: Преглед на 100 кратки текста за правопис/форматиране.

help wanted: Запис на 50 изречения (скрипт в docs/prompts_bul.md).

linguistics: Списък на хомографи за речников модул.

dev: Плъгин за LibreOffice spell-check (Hunspell пакет).

Мини скрипт за запис (пример)
Кажете нормално, без бързане. Ако сгрешите – повторете изречението.
1) Добър ден! Казвам се ____.
2) Българският език живее в нашите гласове.
3) Дигиталното бъдеще започва от днес.
...
## Contributing

We welcome contributions!  
Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## Code of Conduct

This project follows a [Code of Conduct](CODE_OF_CONDUCT.md).  
By participating, you agree to uphold these guidelines.

MIT License

Copyright (c) 2025 Bulgarian-Language-Digital-Future Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Creative Commons Attribution 4.0 International (CC BY 4.0)

You are free to:
- Share — copy and redistribute the material in any medium or format
- Adapt — remix, transform, and build upon the material
for any purpose, even commercially.

Under the following terms:
- Attribution — You must give appropriate credit, provide a link to the license,
  and indicate if changes were made. You may do so in any reasonable manner,
  but not in any way that suggests the licensor endorses you or your use.

Full text of the license: https://creativecommons.org/licenses/by/4.0/

Creative Commons Zero v1.0 Universal (CC0)

The person who associated a work with this deed has dedicated the work to the
public domain by waiving all rights to the work worldwide under copyright law,
including all related and neighboring rights, to the extent allowed by law.

You can copy, modify, distribute and perform the work, even for commercial purposes,
all without asking permission.

Full text of the license: https://creativecommons.org/publicdomain/zero/1.0/
