# Проект структури БД

## Передмова

### Про назви таблиць та полів

## Схема

![medb.png](medb.png "Схема MEdb")

<https://dbdiagram.io/>

## Опис

### equip - таблиця

measuring EQUIPment - вимірювальне обладнання

```sql
Table equip {                                    // measuring EQUIPment
  equ_id        int   [pk, increment]            // id обладнання (unsigned int: up to 16_777_215)
  equ_type      int   [ref: > type.typ_id]       // id > назва обладнання, маркировка
  equ_num       int                              // заводський номер
  equ_prod      year                             // рік випуску
  equ_state     enum('O','P','X')                // Основний/Резервний/Виведений з експлуатації
  equ_trace     int   [ref: > trace.tra_id]      // простежуваність до еталону ? - тут, чи у equ? "traceability"
  equ_branch    int   [ref: > branch.bra_id]     // id метео-станції (замовник)
  equ_usedt     date                             // дата введення в експлуатацію
  equ_caldt     date                             // дата калібрування
  equ_fixdt     date                             // дата останнього ремонту
  equ_setdt     date                             // дата встановлення на метеостанцію
  updt          timestamp                        // дата оновлення
}
}
```
| поле | опис |
| -----| ---- |
| `equ_id`     | id обладнання (unsigned int: up to 16_777_215) |
| `equ_type`   | id > назва обладнання, маркировка |
| `equ_num`    | заводський номер |
| `equ_prod`   | рік випуску |
| `equ_state`  | Основний/Резервний/Виведений з експлуатації |
| `equ_trace`  | простежуваність до еталону ? - тут, чи у equ? "traceability" |
| `equ_branch` | id метео-станції (замовник) |
| `equ_usedt`  | дата введення в експлуатацію |
| `equ_caldt`  | дата калібрування |
| `equ_fixdt`  | дата останнього ремонту |
| `equ_setdt`  | дата встановлення на метеостанцію |
| `updt`       | дата оновлення |





### Таблиця 2

