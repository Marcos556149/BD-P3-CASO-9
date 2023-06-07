# BD-P3-CASO-9
1*) A= π num σ year(fecha) = 2000 LEY
    B= π nomp (σ nomp='San Juan' ∨ nomp='San Luis' ∨ nomp='Mendoza' Prov)
    π num,nomp ρ nomp ← nump (A ⨝ Adhiere) ÷ B
2*) A= (π dni σ partido='Cambiemos' DIP) ⨝ VotosD
    B= (π dnis ρ dnis ← dni σ partido='Cambiemos' SEN) ⨝ VotosS
    π num,nombre (LEY ⨝ ((π num σ voto='SI' A) ∪ (π num σ voto='SI' B)))
3*) A= π NP, N ρ NP ← nump, N ← num Adhiere
    B= Adhiere ⨯ A
    π nump σ nump = NP ∧ num ≠ N ∧ year(fecha) = 2018 B
4*) (π dni, nombre σ prov='San Juan' DIP) ∪ (π dni, nombre σ prov='San Juan' SEN)
5*) A= π nump ρ nump ← nomp Prov
    π num, nombre, cant_art (LEY ⨝ (π num,nump Adhiere ÷ A))
6*) A= π num, dni σ voto='NO' VotosD
    B= π dniD, num ρ dniD ← dni LEY
    C= B⨝A
    D= π dni,num,dniDD,partidoDD ρ dni ← dniD, dniDD ← dni, partidoDD ← partido (C ⨝ DIP)
    E= π partido,dni,num,dniDD,partidoDD (DIP ⨝ D)
    F= π num, nombreL, dni ρ nombreL ← nombre (LEY ⨝ (π num, dni σ partido = partidoDD E))
    π num, nombreL, nombre (DIP ⨝ F)    
