# Simulation numérique de la dynamique des gaz en 1D – Équations d’Euler

## Description
Ce projet traite de la **simulation numérique du système hyperbolique des équations d’Euler en 1D**, qui modélisent la dynamique des gaz compressibles.  
En utilisant la méthode des **volumes finis** et un schéma de flux numérique (Rusanov), l’objectif est de capturer les structures fondamentales d’écoulement : **ondes de choc, ondes de détente et discontinuités de contact**.

Ce travail s’inscrit dans la continuité du TP1 (loi de conservation scalaire) et étend l’approche aux **systèmes 3×3 non linéaires**.

---

## Objectifs
- Analyser les équations d’Euler sous forme conservative :  
  - Conservation de la masse, quantité de mouvement et énergie.  
  - Mise en évidence de la structure hyperbolique via la **matrice Jacobienne** et ses valeurs propres.  
- Étudier le **problème de Riemann** associé aux équations d’Euler.  
- Implémenter un schéma de volumes finis basé sur le **flux de Rusanov**.  
- Valider la simulation sur des cas tests classiques (discontinuités initiales, chocs, détentes, contacts).  
- Vérifier la cohérence physique (invariants de Riemann, inégalités de Lax).  

---

##  Méthodologie
1. **Équations d’Euler en 1D**  
   - Variables d’état : densité (ρ), vitesse (u), pression (p), énergie (E).  
   - Relation d’état pour l’air : γ = 1.4.  
   - Formulation conservative :  
     ```math
     ∂U/∂t + ∂F(U)/∂x = 0
     ```

2. **Analyse mathématique**  
   - Calcul de la matrice Jacobienne A(U).  
   - Détermination des valeurs propres (λ = u−c, u, u+c) → vitesse de propagation des ondes.  
   - Identification des invariants de Riemann.  

3. **Schéma numérique**  
   - Volumes finis avec flux de **Rusanov** :  
     ```math
     F(UL,UR) = 0.5 (F(UL)+F(UR)) − 0.5 λ (UR−UL)
     ```
   - Condition CFL :  
     ```math
     Δt ≤ Δx / (2λ),  λ = max(|u|−c, |u|, |u|+c)
     ```

4. **Tests de validation**  
   - Cas 1 : discontinuité de densité et pression modérée.  
   - Cas 2 : fort contraste de pression.  
   - Comparaison des solutions numériques avec la théorie des ondes (chocs, contacts, détentes).  

---

##  Résultats
- **Ondes de choc** : capturées correctement, mais légèrement diffusées (effet du schéma de Rusanov).  
- **Ondes de contact** : bien reproduites, avec une diffusion numérique visible.  
- **Ondes de détente** : solutions lissées et conformes aux invariants de Riemann.  
- **Validation théorique** : les vitesses respectent les inégalités de Lax → cohérence physique garantie.  

---

## Compétences développées
- **Analyse de PDE hyperboliques non linéaires** (équations d’Euler).  
- Implémentation de **schémas de volumes finis** en 1D.  
- Maîtrise des concepts de **valeurs propres/vecteurs propres, invariants de Riemann**.  
- Validation numérique par comparaison avec la théorie.  
- Utilisation de Python/MATLAB pour la simulation scientifique et la visualisation.  

---

## Organisation
- `TP2_système_hyperbolique_2024_2025.pdf` → Rapport complet avec explications et résultats.  
- `code/` → Implémentation numérique (Python ou MATLAB).  
- `figures/` → Résultats visuels des tests (chocs, contacts, détentes).  
- `README.md` → Présentation détaillée du projet.  

---

##  Perspectives
- Utilisation de schémas plus précis (**HLLC, Roe, solveurs de Riemann exacts**).  
- Extension en **2D** pour simuler des écoulements complexes.  
- Étude de cas réels : jets supersoniques, dynamique des chocs, écoulements astrophysiques.  
- Réduction de la diffusion numérique via des schémas TVD (Total Variation Diminishing).  

---

##  Conclusion:
Ce projet démontre :  
- Une **maîtrise solide en calcul scientifique et simulation numérique**.  
- La capacité à **analyser et implémenter des algorithmes avancés** pour résoudre des systèmes hyperboliques.  
- Une compréhension des **phénomènes physiques** associés aux écoulements compressibles.  
- Des compétences transférables en **modélisation, ingénierie numérique, mécanique des fluides et data science**.

  
## Auteur
**Bréhima Samaké**  
Février 2025  

---
