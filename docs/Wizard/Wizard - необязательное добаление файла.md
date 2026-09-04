site_name: WorkWiki
# Wizard - пропуск шага с добавлением файла

## 📎 Общее описание
Конструкция позволяет пропустить шаг с добавлением файла, если этот файл является необязательным в рамках мероприятия.

---

## 📌 Пример использования

**Шаблон мероприятия в 1С:** Летняя биологическая школа – 2026

**Код:** `000000883`

## 🧙 Wizard

```
{
    "version": 0.13,
    "DocState": {
        "Pending": "43142b94-34f1-11f1-a85f-005056b8fc44",
        "Accepted": "43142b95-34f1-11f1-a85f-005056b8fc44",
        "Rejected": "b213961b-43b3-11f1-a85f-005056b8fc44"
    },
"customFilter": [
{
"show_badge": true,
  "key": "need_hostel",
  "type": "boolean",
  "label": "Проживание",
  "title": "Нуждаемость в проживании",
  "mode": "checkbox",
  "multi": true,
  "selection_rule": "exclusive_false",
  "LineWizardGUID": "618db432-73dc-4e6c-a291-b47b3dc29171",
  "prop": {
    "name": "AccommodationFormat",
    "bool_map": {
      "true": "Нужно проживание",
      "false": "Без проживания"
    }
  }
}
],
    "Stages": [
        {
            "Name": "WizardStep1",
            "accrual_month": "2026-06-01",
            "WizardStageGUID": "ba7d63d9-3361-11f1-8fdd-005056b872b3",
            "Start": {
                "Stage": "WizardStep1",
                "Status": "InProgress"
            },
            "End": {
                "Success": {
                    "Stage": "WizardStep1",
                    "Status": "Accept"
                },
                "Fail": {
                    "Stage": "WizardStep1",
                    "Status": "Reject",
"display":true
                }
            },
            "Correction": {
                "Stage": "WizardStep1",
                "Status": "OnCorrection"
            },
            "Review": {
                "Stage": "WizardStep1",
                "Status": "OnReview"
            },
            "IsMember": {
                "Stage": "WizardStep1",
                "Status": "IsMember"
            },
            "WizardSteps": [
                {
                    "key": 1,
                    "type": "welcome",
                    "name": "Загрузка документов на ''Летнюю биологическую смену 2026''",
                    "required": true,
                    "view": {
                        "kind": "html",
                        "html": "<div class=\"welcome-step-header\">\n  <p class=\"welcome-step-description\">Подготовьте документы указанные в списке ниже (при наличии):</p>\n</div>\n<div class=\"welcome-step-grid\">\n  <div class=\"welcome-step-section\">\n    <h3 class=\"welcome-step-section-title\">Список документов:</h3>\n    <ul class=\"welcome-step-list\">\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\">Диплом победителя олимпиады по биологии, экологии и/или химии;</span>\n      </li>\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\">Справка от Соцзащиты (о признании семьи/гражданина малоимущей(им).</span>\n      </li>\n    </ul>\n  </div>\n  <div class=\"welcome-step-section\">\n    <h3 class=\"welcome-step-section-title\">Как всё устроено:</h3>\n    <ul class=\"welcome-step-list\">\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\"> Заполните все поля в каждом шаге мастера, где это необходимо</span>\n      </li>\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\"> Прикрепите файлы документов (при наличии)</span>\n      </li>\n          <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\"> По окончанию подачи документов ожидайте результатов проверки и ссылку на оплату</span>\n      </li>\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\"> Уведомления будут направлены на адрес электронной почты, указанной при регистраиции</span>\n      </li>\n    </ul>\n  </div>\n   <h3 class=\"welcome-step-section-title2\">ВАЖНО! РЕБЕНОК СЧИТАЕТСЯ ЗАЧИСЛЕННЫМ НА СМЕНУ ТОЛЬКО ПОСЛЕ ОПЛАТЫ!</h3>\n   </div>"
                    }
                },
                {
                    "key": 2,
                    "type": "getDocs",
                    "required": true,
                    "requireFile": false,
                    "view": {
                        "kind": "html",
                        "html": "<div class=\"welcome-step-header\">\n  <p class=\"welcome-step-description\">Летняя смена имеет ограничения для участников. Укажите школу и  какой класс окончен участником. <br>Принять участие могут:</p>\n</div>\n<div class=\"welcome-step-grid\">\n  <div class=\"welcome-step-section\">\n    <h3 class=\"welcome-step-section-title\">Лицеисты, в 2026 году поступающие в:</h3>\n    <ul class=\"welcome-step-list\">\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\">6 класс - без ограничений;</span>\n      </li>\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\">7-9 классы химико-биологического и биофизического направления.</span>\n      </li>\n    </ul>\n  </div>\n  <div class=\"welcome-step-section\">\n    <h3 class=\"welcome-step-section-title\">Поступившие в рамках приемной кампании в 2026 году в:</h3>\n    <ul class=\"welcome-step-list\">\n      <li class=\"welcome-step-list-item\">\n        <span class=\"welcome-step-text\">7-9 классы химико-биологического и биофизического направления.</span>\n      </li>\n    </ul>\n  </div>\n  <div class=\"welcome-step-section\">\n   </div>"
                    },
                    "typeDocs": [
                        "46912a89-3d9c-11f1-a85f-005056b8fc44"
                    ],
                    "name": "Условия участия",
                    "StepGUID": "d651bdad-ee05-458d-8e76-0fe4fdb021a8",
                    "ext": [
                        {
                            "View": "В какой класс переходите или в какой класс приглашены",
                            "Type": "8bfaa960-33f2-11f1-8fdd-005056b872b3",
                            "Visibility": true,
                            "ParamName": "finishedClass"
                        }
                    ]
                },
                {
                    "key": 3,
                    "type": "getDocs",
                    "required": true,
                    "requireFile": false,
                    "view": {
                        "kind": "html",
                        "html": "<div class=\"welcome-step-description\">Летняя школа имеет два формата проведения - с проживанием и без. Укажите, в каком формате вы будете принимать участие.</div>"
                    },
                    "typeDocs": [
                        "46912a89-3d9c-11f1-a85f-005056b8fc44"
                    ],
                    "name": "Формат участия",
                    "StepGUID": "618db432-73dc-4e6c-a291-b47b3dc29171",
                    "ext": [
                        {
                            "View": "Формат участия",
                            "Type": "6c791b26-4474-11f1-a85f-005056b8fc44",
                            "Visibility": true,
                            "ParamName": "AccommodationFormat"
                        }
                    ]
                },
                {
                    "key": 4,
                    "type": "getDocs",
                    "required": false, ==ОБЯЗАТЕЛЬНО==
                    "view": {
                        "kind": "html",
                        "html": "<div class=\"welcome-step-description\">Укажите сведения о наличии достижений для предоставления льготы. Если участник является победителем муниципального этапа олимпиад по биологии, экологии, химии - прикрепите подтверждающие документы.</div>"
                    },
                    "typeDocs": [
                        "46912a89-3d9c-11f1-a85f-005056b8fc44"
                    ],
                    "name": "Диплом олимпиады",
                    "StepGUID": "790127e7-c36d-42ff-a175-7baedf991dd0" ==ОБЯЗАТЕЛЬНО==
                },
                {
                    "key": 5,
                    "type": "getDocs",
                    "required": false, ==ОБЯЗАТЕЛЬНО==
                    "view": {
                        "kind": "html",
                        "html": "<div class=\"welcome-step-description\">Укажите сведения о наличии статуса малоимущей семьи. Если у родителя участника есть справка о признании семьи (гражданина) малоимущей(им), прикрепите подтверждающие документы.</div>"
                    },
                    "typeDocs": [
                        "46912a89-3d9c-11f1-a85f-005056b8fc44"
                    ],
                    "name": "Справка от соцзащиты",
                    "StepGUID": "2b11b88f-a30c-4ab3-ad30-e00b4a7498f4" ==ОБЯЗАТЕЛЬНО==
                }
            ]
        }
    ]
}
```

---

## 🔥 Ключевые элементы

 - [required: false — поле не обязательное]

 - [StepGUID — идентификатор шага]
 
```
    ...
    {
        "key": 4,
        "type": "getDocs",
        "required": false, ==ОБЯЗАТЕЛЬНО==
        "view": {
            "kind": "html",
            "html": "<div class=\"welcome-step-description\">Укажите сведения о наличии достижений для предоставления льготы. Если участник является победителем муниципального этапа олимпиад по биологии, экологии, химии - прикрепите подтверждающие документы.</div>"
        },
        "typeDocs": [
            "46912a89-3d9c-11f1-a85f-005056b8fc44"
        ],
        "name": "Диплом олимпиады",
        "StepGUID": "790127e7-c36d-42ff-a175-7baedf991dd0" ==ОБЯЗАТЕЛЬНО==
    },
    ...

```


---

## 🖼️ Отображение

На стороне пользователя, данное решение позволяет или прикрепить файл, при его наличии, или пропустить шаг. Может применяться для предоставления документов о наличии льгот или дипломов олимпиад.