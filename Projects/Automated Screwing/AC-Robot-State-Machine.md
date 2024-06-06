
## Home Position

|    **State**    |    **WQR ON**    |   **WQR OFF**    |
| :-------------: | :--------------: | :--------------: |
|   **WQL ON**    | CALL AA_INTPOSLH | CALL AA_INTPOSLH |
|   **WQL OFF**   | CALL AA_INTPOSRH |       LOOP       |

## Intermediate Position Left

|  **State**  |    **WQR ON**    |   **WQR OFF**    |
| :---------: | :--------------: | :--------------: |
| **WQL ON**  | CALL AA_PREPOSLH | CALL AA_PREPOSLH |
| **WQL OFF** |   CALL AA_HOME   |   CALL AA_HOME   |

## Pre Position Left (After Process)

|  **State**  |    **WQR ON**    |   **WQR OFF**    |
| :---------: | :--------------: | :--------------: |
| **WQL ON**  |        -         |        -         |
| **WQL OFF** | CALL AA_INTPOSLH | CALL AA_INTPOSLH |
*WQL is turned OFF after screwing process*

## Intermediate Position Right

|  **State**  |    **WQR ON**    | **WQR OFF**  |
| :---------: | :--------------: | :----------: |
| **WQL ON**  | CALL AA_PREPOSRH | CALL AA_HOME |
| **WQL OFF** | CALL AA_PREPOSRH | CALL AA_HOME |

## Pre Position Right (After Process)

|  **State**  | **WQR ON** |   **WQR OFF**    |
| :---------: | :--------: | :--------------: |
| **WQL ON**  |     -      | CALL AA_INTPOSRH |
| **WQL OFF** |     -      | CALL AA_INTPOSRH |
