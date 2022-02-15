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
Table equip {                                    //
  equ_id        int   [pk, increment]            //
  equ_type      int   [ref: > type.typ_id]       //
  equ_num       int                              //
  equ_prod      year                             //
  equ_state     enum('O','P','X')                //
  equ_trace     int   [ref: > trace.tra_id]      //
  equ_branch    int   [ref: > branch.bra_id]     //
  equ_usedt     date                             //
  equ_caldt     date                             //
  equ_fixdt     date                             //
  equ_setdt     date                             //
  updt          timestamp                        //
}
```

|  equ_id     |  id обладнання (unsigned int: up to 16_777_215) |
|  equ_type   |  id > назва обладнання, маркировка |
|  equ_num    |  заводський номер |
|  equ_prod   |  рік випуску |
|  equ_state  |  Основний/Резервний/Виведений з експлуатації |
|  equ_trace  |  простежуваність до еталону ? - тут, чи у equ? "traceability" |
|  equ_branch |  id метео-станції (замовник) |
|  equ_usedt  |  дата введення в експлуатацію |
|  equ_caldt  |  дата калібрування |
|  equ_fixdt  |  дата останнього ремонту |
|  equ_setdt  |  дата встановлення на метеостанцію |
|  updt       |  дата оновлення |




### Таблиця 2

