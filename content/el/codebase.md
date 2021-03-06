## I. Βάση Κώδικα
### Μία βάση κώδικα με έλεγχο εκδόσεων, πολλές αναπτύξεις

Μια εφαρμογή δώδεκα παραγόντων είναι πάντα διαχειριζόμενη από ένα σύστημα ελέγχου εκδόσεων κώδικα (version control system), όπως το [Git](http://git-scm.com/), το [Mercurial](https://www.mercurial-scm.org/), ή το [Subversion](http://subversion.apache.org/).  Ένα αντίγραφο της βάσης αλλαγών του συστήματος είναι γνωστό ως *αποθετήριο κώδικα* (*code repository*), συχνά συντομευμένο σε *αποθετήριο* (*code repo* ή *repo*).

Μια *βάση κώδικα* (*codebase*) είναι είτε ένα οποιοδήποτε αποθετήριο (σε ένα κεντρικά διαχειριζόμενο σύστημα όπως το Subversion), είτε ένα οποιοδήποτε σύνολο από αποθετήρια τα οποία μοιράζονται μία κοινή ρίζα εισαγωγής κώδικα (σε ένα αποκεντρωμένο σύστημα διαχείρισης όπως το Git).

![Μία βάση κώδικα αναλογεί σε πολλές αναπτύξεις της εφαρμογής](/images/codebase-deploys.png)

Υπάρχει πάντα μια σχέση ένα-προς-ένα μεταξύ της βάσης κώδικα και της εφαρμογής:

* Αν υπάρχουν πολλαπλές βάσεις κώδικα, δεν είναι εφαρμογή -- είναι ενα κατανεμημένο σύστημα. Κάθε μέρος του κατανεμημένου συστήματος είναι εφαρμογή, και το καθένα ξεχωριστά μπορεί να συνάδει με τους δώδεκα παράγοντες.
* Πολλαπλές εφαρμογές οι οποίες μοιράζονται τον ίδιο κώδικα συνιστά παράβαση των δώδεκα παραγόντων.  Η λύση εδώ είναι να παραγοντοποιηθεί ο κοινός κώδικας σε βιβλιοθήκες οι οποίες μπορούν να εισαχθούν μέσω του [διαχειριστή εξαρτήσεων](./dependencies).

Υπάρχει μόνο μία βάση κώδικα ανά εφαρμογή, αλλά θα υπάρξουν πολλές αναπτύξεις της εφαρμογής.  Μια *ανάπτυξη* (*deploy*) της εφαρμογής, είναι μία εκτελούμενη ενσάρκωση της εφαρμογής.  Αυτό τυπικά είναι μία τοποθεσία παραγωγής (production site), και μία ή περισσότερες τοποθεσίες ελέγχου (staging sites).  Επιπλέον, κάθε προγραμματιστής έχει ένα αντίγραφο της εφαρμογής εκτελούμενο τοπικά στο περιβάλλον του, το οποίο επίσης συνιστά μια ανάπτυξη.

Η βάση κώδικα είναι η ίδια για όλες τις αναπτύξεις, παρόλαυτά διαφορετικές εκδόσεις κώδικα μπορεί να είναι ενεργές ανά ανάπτυξη.  Για παράδειγμα, ο προγραμματιστής έχει κάποιες αλλαγές που δεν έχουν ακόμα κατατεθεί στην τοποθεσία ελέγχου, η τοποθεσία ελέγχου έχει κάποιες αλλαγές που δεν έχουν ακόμα κατατεθεί στην παραγωγή.  Αλλά όλα μοιράζονται την ίδια βάση κώδικα, έτσι μπορούν να ταυτοποιηθούν ως διαφορετικές αναπτύξεις της ίδιας εφαρμογήε.

