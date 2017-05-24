```clj
(ns humpty.core
  (require [clojure.set :refer [subset?]]))
```

# Humpty Dumpty

Humpty Dumpty 

```clj
  (def humpty (atom {:name "Humpty Dumpty"}))
```

sat on a wall,

```clj
  (swap! humpty assoc :status "sitting on wall")
```

Humpty Dumpty had a great fall.

```clj
  (swap! humpty assoc :status "broken")
```

All the king's horses

```clj
  ; the world has horses,
  (def horses
   [{:owner "The King"}
    {:owner "The King"}
    {:owner "Moses"}
    {:owner "Moses"}
    {:owner "The King"}
    {:owner "The King"}
    {:owner "Catherine"}
    {:owner "Catherine"}
    {:owner "The King"}
    {:owner "The King"}])

  ;some of which are the king's:
  (def kings-horses
    (filter (fn [horse] (= "The King" (horse :owner))) horses))
```

and all the king's men

```clj
  ; the world has men,
  (def men
   [{:loyalty "The King"      :occupation "Soldier"}
    {:loyalty "Science"       :occupation "Chemist"}
    {:loyalty "God"           :occupation "Priest"}
    {:loyalty "The King"      :occupation "Jester"}
    {:loyalty "Himself"       :occupation "Dilettante"}
    {:loyalty "The King"      :occupation "Cobbler"}
    {:loyalty "The King"      :occupation "Serf"}
    {:loyalty "The King"      :occupation "Knight"}
    {:loyalty "Another King"  :occupation "Knight"}
    {:loyalty "The King"      :occupation "Mechanical Engineer"}])

  ; some of whom are the king's:
  (def kings-men 
    (filter (fn [man] (= "The King" (man :loyalty))) men))
```

Couldn't put Humpty together again.

```clj
  (defn can-fix-egg?
    [men]
    (and 
      ; must have 5 men
      (>= (count men) 5)
      ; must have a chemist, mechanical engineer, and dilettante
      (subset? #{"Chemist" "Mechanical Engineer" "Dilettante"} 
               (set (map :occupation men)))))

  (defn fix-egg
    [men egg]
    (when (can-fix-egg? men) (swap! egg assoc :status "fixed")))
```

```clj

  (can-fix-egg? kings-men)
  => false

  (fix-egg! kings-men humpty)
  => {:name "Humpty Dumpty" :status "broken"}
```

Maybe if they had learned to cooperate...

```clj

  (can-fix-egg? men)
  => true

```


# Humpty Dumpty
_Append-Only Twitter Edition_

```clj
  (def users (atom {}))
  (def tweets (atom []))
```

Humpty Dumpty sat on the wall

```clj
  (swap! tweets conj 
         {:user "humpty-dump" 
          :body "chillin on the wall yo"
          :photo "http://goo.gl/dEK6En"
          :bio "Philosopher, poet, egg."
          :time "3:43 pm wed sept 17 2014"})

```

Humpty Dumpty had a great fall

```clj
  (swap! tweets conj 
         {:user "jonathan_4_eva" 
          :body "whoa did you see that thing fall off the wall!?!?!"
          :bio "farmer, father, I like to carve wheat"
          :time "3:48 pm wed sept 17 2014"})

  (swap! tweets conj 
         {:user "sweet_rose" 
          :body "Did anyone else just hear a big crash??"
          :bio "fresh produce, best deal in town"
          :time "3:49 pm wed sept 17 2014"})

  (swap! tweets conj 
         {:user "CastleKnightBrigade43" 
          :body "We are investigating an incident at the wall"
          :bio "serve and protect"
          :time "3:49 pm wed sept 17 2014"})
```

All the king's horses and all the king's men

```clj
  (swap! tweets conj 
         {:user "CastleKnightBrigade43" 
          :body "all clear the road, we're moving in"
          :bio "serve and protect"
          :time "3:59 pm wed sept 17 2014"})

  (swap! tweets conj 
         {:user "bacon_" 
          :body "Humpty we believe in u, pull thru this man"
          :bio "i play music"
          :time "4:02 pm wed sept 17 2014"})

  (swap! tweets conj 
         {:user "sweet_rose" 
          :body "horses have trampled my garden AGAIN. #fml"
          :bio "fresh produce, best deal in town"
          :time "4:12 pm wed sept 17 2014"})
```

Couldn't put Humpty together again.


```clj
  (swap! tweets conj 
         {:user "CastleKnightBrigade43" 
          :body "Regret to inform subjects that Humpty Dumpty has passed away. Cause of death blunt head trauma due to fall from city wall."
          :bio "serve and protect"
          :time "4:20 pm wed sept 17 2014"})

  (swap! tweets conj 
         {:user "bacon_" 
          :body ":("
          :bio "i play music"
          :time "5:49 pm wed sept 17 2014"})

```
