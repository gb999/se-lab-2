
 Tries to fire the torpedo stores of the ship.
  @param firingMode how many torpedo bays to fire

**SINGLE**: fires only one of the bays.
- For the first time the primary store is fired.
- To give some cooling time to the torpedo stores, torpedo stores are fired alternating.
- But if the store next in line is empty, the ship tries to fire the other store.
- If the fired store reports a failure, the ship does not try to fire the other one.

 **ALL**:	tries to fire both of the torpedo stores.
  @return whether at least one torpedo was fired successfully
  
# Parancsok 
`GT4500,<PRIMARY_COUNT>,<PRIMARY_FAILURE_RATE>,<SECONDARY_COUNT>,<SECONDARY_FAILURE_RATE>`
`TORPEDO,<FIRING_MODE : SINGLE | ALL>`  

## 1. tud lőni
|                           |                                                          |
| ------------------------- | -------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 tud egy fegyverrel tüzelni                      |
| ELŐFELTÉTELEK             | Egy GT4500, mindkét torpedó betöltve, nincs meghibásodás |
| A TESZT LÉPÉSEI           | tüzelés 1 torpedóval                                     |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS                                                  |
|  |                                                          |

## 2. 1. tüzelés
|                           |                                                          |
| ------------------------- | -------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 tud az 1. fegyverrel tüzelni                    |
| ELŐFELTÉTELEK             | Egy GT4500, 1. torpedó betöltve, nincs meghibásodás |
| A TESZT LÉPÉSEI           | tüzelés 1 torpedóval                                                          |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS                                                          |

## 3. 2. tüzelés
|                           |                                                          |
| ------------------------- | -------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 tud a 2. fegyverrel tüzelni                    |
| ELŐFELTÉTELEK             | Egy GT4500, 2. torpedó betöltve, nincs meghibásodás |
| A TESZT LÉPÉSEI           | tüzelés 1 torpedóval                                                          |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS                                                          |


## 4. nincs betöltve  
|                           |                                   |
| ------------------------- | --------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 nem tud tüzelni, ha üres |
| ELŐFELTÉTELEK             | nincs betöltött torpedo           |
| A TESZT LÉPÉSEI           | tüzelés                           |
| ELVÁRT KIMENET / EREDMÉNY | FAIL                              |
|                           |                                   |

## 5. hibás 
|                           |                                                                |
| ------------------------- | -------------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 nem tud tüzelni, ha meghibásodik                      |
| ELŐFELTÉTELEK             | mindkét torpedo be van töltve, a meghibásodás valószínűsége 1. |
| A TESZT LÉPÉSEI           | tüzelés                                                        |
| ELVÁRT KIMENET / EREDMÉNY | FAIL                                                           |
|                           |                                                                
## 6. alternál-e
|                           |                                                                |
| ------------------------- | -------------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 alternálva lő                      |
| ELŐFELTÉTELEK             | mindkét torpedo be van töltve, a meghibásodás valószínűsége 0. |
| A TESZT LÉPÉSEI           | 2 tüzeléstüzelés                                                        |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS SUCCESS                                                        |
|                           |                                                                

## 7. All 2 betöltve
|                           |                                                                |
| ------------------------- | -------------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 lő ha mindkét torpedóval tüzeln próbál                |
| ELŐFELTÉTELEK             | mindkét torpedo be van töltve, a meghibásodás valószínűsége 0. |
| A TESZT LÉPÉSEI           | lövés ALL módban                                               |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS                 |
|                           |                                                                |

## 8. All 1 betöltve
|                           |                                                                |
| ------------------------- | -------------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 lő ha mindkét torpedóval tüzeln próbál                |
| ELŐFELTÉTELEK             | 1 torpedo van betöltve, a meghibásodás valószínűsége 0. |
| A TESZT LÉPÉSEI           | lövés ALL módban                                               |
| ELVÁRT KIMENET / EREDMÉNY | SUCCESS                 |
|                           |                                                                |
## 9. All nincs betöltve
|                           |                                                                |
| ------------------------- | -------------------------------------------------------------- |
| TESZTELT KÖVETELMÉNY      | A GT4500 lő ha mindkét torpedóval tüzeln próbál                |
| ELŐFELTÉTELEK             | nincs torpedp betöltve, a meghibásodás valószínűsége 0. |
| A TESZT LÉPÉSEI           | lövés ALL módban                                               |
| ELVÁRT KIMENET / EREDMÉNY | FAIL                 |
|                           |                                                                |


# + 
## 10. 2. aztan 1.
