# Общие переменные

## ИМЯ РЕБЕНКА

```
      // ИМЯ РЕБЕНКА
    "candidate_lastname": { "source": "candidate", "path": "Lastname" },
    "candidate_firstname": { "source": "candidate", "path": "Name" },
    "candidate_middlename": { "source": "candidate", "path": "Surname" },
      
      // ПОЛНОЕ ИМЯ РЕБЕНКА
    "candidate_full_name": {
      "op": "concat",
      "sep": " ",
      "parts": [
        { "source": "candidate", "path": "Lastname" },
        { "source": "candidate", "path": "Name" },
        { "source": "candidate", "path": "Surname" }
      ],
      "required": true
    },

```
## ДАТА РОЖДЕНИЯ РЕБЕНКА

```
// ДАТА РОЖДЕНИЯ РЕБЕНКА
    "candidate_birthday": { "op": "formatDate", "value": { "source": "candidate", "path": "Birthday" }, "format": "dd.MM.yyyy" },
    "children_birthday": { "$ref": "#/candidate_birthday" },
      
    "candidate_gender": { "source": "candidate", "path": "Gender" },
    "candidate_gender_rod_word": { "op": "genderToRod", "value": { "source": "candidate", "path": "Gender" }, "male": "сына", "female": "дочь", "unknown": "ребёнка" },
```

## АДРЕС РЕБЕНКА
```
// АДРЕС РЕБЕНКА
    "candidate_address_reg": { "op": "first", "value": { "op": "contactsByType", "type": "Адрес" } },
      
    "candidate_phones": { "op": "join", "sep": ", ", "value": { "op": "contactsByType", "type": "Телефон" } },
    "candidate_emails": { "op": "join", "sep": ", ", "value": { "op": "contactsByType", "type": "Адрес электронной почты" } },
```

## ДАННЫЕ СВИДЕТЕЛЬСТВА О РОЖДЕНИИ
```
    // ДАННЫЕ СВИДЕТЕЛЬСТВА О РОЖДЕНИИ
    "birth_cert_series": { "source": "wizard", "path": "birthCertificate.series" },
    "birth_cert_number": { "source": "wizard", "path": "birthCertificate.number" },
    "birth_cert_issue_date": { "op": "formatDate", "value": { "source": "wizard", "path": "birthCertificate.issueDate" }, "format": "dd.MM.yyyy" },
    "birth_cert_issued_by": { "source": "wizard", "path": "birthCertificate.issuedBy" },
      
    "birth_cert_registration_address": { "source": "wizard", "path": "birthCertificate.registrationAddress" },
    "birth_cert_phone": { "source": "wizard", "path": "birthCertificate.phone" },
    "birth_cert_email": { "source": "wizard", "path": "birthCertificate.email" },
    "birth_cert_asset_id": { 
      "source": "wizard", 
      "path": "birthCertificate.files[0]?.assetId" 
    },
```

## ДАТА
```
 "write_day": { "source": "now", "format": "dd" },
    "write_month": { "source": "now", "format": "MMMM" },
    "write_year": { "source": "now", "format": "yyyy" },
```

## ИМЯ РОДИТЕЛЯ

```
    "statement_parent_full_name": { "source": "wizard", "path": "statementPassport.fullName" },
```
      
## ПАСПОРТ РОДИТЕЛЯ
```
    "statement_parent_passport_text": {
      "op": "formatPassport",
      "series": { "source": "wizard", "path": "statementPassport.series" },
      "number": { "source": "wizard", "path": "statementPassport.number" },
      "issuedBy": { "source": "wizard", "path": "statementPassport.issuedBy" },
      "issueDate": { "op": "formatDate", "value": { "source": "wizard", "path": "statementPassport.issueDate" }, "format": "dd.MM.yyyy" }
    },
```

## ДАТА РОЖДЕНИЯ РОДИТЕЛЯ

```
    "statement_parent_birth_date": { 
      "op": "formatDate", 
      "value": { "source": "wizard", "path": "statementPassport.birthDate" }, 
      "format": "dd.MM.yyyy" 
    },
```  

      
## АДРЕС РЕГИСТРАЦИИ РОДИТЕЛЯ

```
    "statement_parent_reg_address": { 
      "source": "wizard", 
      "path": "statementPassport.registrationAddress" 
    },
      
    "statement_passport_source": { 
      "source": "wizard", 
      "path": "statement.parentPassportSource" 
    },
    "snils_number": { 
      "source": "wizard", 
      "path": "snils.number" 
    },
    
```
      
## НОМЕР ТЕЛЕФОНА И ПОЧТА РОДИТЕЛЕЙ

```
    "phone1": { "source": "wizard", "path": "parentPassport1.phone" },
    "phone2": { "source": "wizard", "path": "parentPassport2.phone" },
    "statement_phone": { "source": "wizard", "path": "statementPassport.phone" },
      
    "email1": { "source": "wizard", "path": "parentPassport1.email" },
    "email2": { "source": "wizard", "path": "parentPassport2.email" },
    "statement_email": { "source": "wizard", "path": "statementPassport.email" },
```

## ДОПОЛНИТЕЛЬНЫЕ ПАРАМЕТРЫ
 ```
 "school_name": { "source": "static", "value": "название текущей школы" },
    "target_class": { "source": "static", "value": "5" },
 ```
      
      
   