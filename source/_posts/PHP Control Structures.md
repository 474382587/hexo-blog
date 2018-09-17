---
title: PHP Control Structures
date: 2018-09-14 11:15:07
tags: [PHP]
---

## Control Structures
---
- ### if
- ### else
- ### else if/ elseif
    ```php
    <?php
    if($condition) {
      // do this
    }
    else if{
      // do that
    }
    else {
      // do this
    }
    ?>
    ```
---

- ### switch
    ```php
    <?php
    switch ($condition)
      case 'value1':
        // code 1
        break;
      case 'value2':
        // code 2
        break;
      case 'value3':
        // code 3
        break;
      default:
        // code default
        break;
    endswitch;
    ?>

    ---

    <?php
    switch ($condition) {
      case 'value1':
        // code 1
        break;
      case 'value2':
        // code 2
        break;
      case 'value3':
        // code 3
        break;
      default:
        // code default
        break;
    }
    ?>

    ---

    <?php
    switch ($condition) {
      case 'value1': {
        // code 1
        break;
      }
        
      case 'value2': {
        // code 2
        break;
      }
        
      case 'value3': {
        // code 3
        break;
      }
        
      default: {
        // code default
        break;
      }
    }
    ?>
    ```

---

- ### while
  
    ```php
    <?php
    /* example 1 */

    $i = 1;
    while ($i <= 10) {
        echo $i++;  /* the printed value would be
                      $i before the increment
                      (post-increment) */
    }

    /* example 2 */

    $i = 1;
    while ($i <= 10):
        echo $i;
        $i++;
    endwhile;
    ?>
    ```
---

- ### do - while
    ```php
    <?php
    $i = 0;
    do {
        echo $i;
    } while ($i > 0);
    ?>
    ```
---
- ### for 
    ```php
    <?php
      for (exp1, exp2, exp3) {
        // code
      }
    ?>

    <?php
    /* example 1 */

    for ($i = 1; $i <= 10; $i++) {
        echo $i;
    }

    /* example 2 */

    for ($i = 1; ; $i++) {
        if ($i > 10) {
            break;
        }
        echo $i;
    }

    /* example 3 */

    $i = 1;
    for (; ; ) {
        if ($i > 10) {
            break;
        }
        echo $i;
        $i++;
    }

    /* example 4 */

    for ($i = 1, $j = 0; $i <= 10; $j += $i, print $i, $i++);
    ?>
    ```
---

- ### break, continue
  - **continue is used within looping structures to skip the rest of the current loop iteration and continue execution at the condition evaluation and then the beginning of the next iteration.**
    ```php
      <?php
      foreach ($arr as $key => $value) {
          if (!($key % 2)) { // skip even members
              continue;
          }
          do_something_odd($value);
      }

      $i = 0;
      while ($i++ < 5) {
          echo "Outer<br />\n";
          while (1) {
              echo "Middle<br />\n";
              while (1) {
                  echo "Inner<br />\n";
                  continue 3;
              }
              echo "This never gets output.<br />\n";
          }
          echo "Neither does this.<br />\n";
      }
      ?>
    ```
  - **break ends execution of the current for, foreach, while, do-while or switch structure.**
    ```php
      <?php
      $arr = array('one', 'two', 'three', 'four', 'stop', 'five');
      foreach ($arr as $val) {
          if ($val == 'stop') {
              break;    /* You could also write 'break 1;' here. */
          }
          echo "$val<br />\n";
      }

      /* Using the optional argument. */

      $i = 0;
      while (++$i) {
          switch ($i) {
              case 5:
                  echo "At 5<br />\n";
                  break 1;  /* Exit only the switch. */
              case 10:
                  echo "At 10; quitting<br />\n";
                  break 2;  /* Exit the switch and the while. */
              default:
                  break;
          }
      }
      ?>
    ```