import numpy as np

# Datos del problema a diseñar
d_1 = 15; # Longitud de A hasta B [mm]
d_2 = 6,25; # Longitud de D hasta A [mm]
d_3 = 50; # Longitud de B hasta la Fuerza T [mm]
d_4 = 62,5; # Longitud de A hasta B [mm]
Tmax = 100; # Fuerza maxima [N]
Tmin = 0; # Fuerza minima [N]

# Transformación de [mm] --> [m]
D1 = d_1/1000
D2 = d_2/1000
D3 = d_3/1000
D4 = d_4/1000

#Calculo inicial del ángulo
Teta_ = A_g(D1,D2,D3)

#Lazo de cálculo para estimar D_c y Q_c

for i in range(0,100):
    if Tmin < T < Tmax:
        F_BD(T,Teta,D1,D3,D4)
        F_Ax(BD,Teta)
        F_Ay(BD,Teta,T)
    else: 
        if T > Tmax:
            F_BD(T,Teta,D1,D3,D4)
            F_Ax(BD,Teta)
            F_Ay(BD,Teta,T)
    if T < Tmin:
        T = 0 
    end
end         

print(BD,Ax,Ay)

#AlexisAguilarGR3S1

#Resolución completa de un ejercicio de Mecánica de Materiales
