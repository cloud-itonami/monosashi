#!/usr/bin/env bb
;; monosashi 物差し — bb-native test runner (Clojure / babashka; no shell, per ADR-2606072802).
;;
;;   bb test
(require '[clojure.test :as t])

(def suites
  '[monosashi.tests.test-score
    monosashi.tests.test-social])

(apply require suites)

(let [{:keys [fail error]} (apply t/run-tests suites)]
  (if (zero? (+ fail error))
    (println "── monosashi: ALL suites green ──")
    (do (println "── monosashi: FAILURES above ──")
        (System/exit 1))))
