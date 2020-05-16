# Carp Destructure Macro

```clojure
(deftype AnExample [field-one Int field-two Int])

; Destructure using field name
(des [(field-two field-one) (AnExample.init 1 2)]
  (do 
   (println* field-two)
   (println* field-one)))

; Destructure with rename
(des [((some-one field-two) (some-two field-one)) (AnExample.init 1 2)]
  (do 
   (println* some-two)
   (println* some-one)))

; Destructure using field order
(des [[name-one name-two] (AnExample.init 1 2)]
  (do 
   (println* name-one)
   (println* name-two)))

; Destructure multiple things
(des [[name-one name-two] (AnExample.init 1 2)
      [wow-one wow-two] (AnExample.init 6 3)]
  (do 
   (println* name-one)
   (println* name-two)
   (println* wow-one)
   (println* wow-two)))

; Can also act like `let`
(des [example (AnExample.init 1 2)
      [wow-one wow-two] (AnExample.init 6 3)]
  (do 
   (println* example)
   (println* wow-one)
   (println* wow-two)))

; Don't have to use everything
(des [(field-two) (AnExample.init 1 2)]
  (do 
   (println* field-two)))
```
