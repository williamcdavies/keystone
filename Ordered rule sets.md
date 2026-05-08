---
tags:
  - CS658
---
An ordered rule set is known as a decision list. Rules are rank ordered according to their priority. For example, when a test record is presented to the classifier, it is assigned to the class label of the highest ranked rule it has triggered. If none of the rules fired, it is assigned to the default class.

That is, if more than one rule is triggered, need conflict resolution:
- Size ordering - assign the highest priority to the triggering rules that has the “toughest” requirement (i.e., with the most attribute test)
- Class-based ordering - decreasing order of prevalence or misclassification cost per class
- Rule-based ordering (decision list) - rules are organised into one long priority list, according to some measure of rule quality or by experts