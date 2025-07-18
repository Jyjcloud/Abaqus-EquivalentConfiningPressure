#Method Supplement

This project provides a method for applying “equivalent confining pressure” within the Abaqus explicit dynamic framework. It is particularly suitable for structures where conventional pressure loading is difficult to apply, such as topologically interlocking structures and chainmail-like particle systems. This method has been employed in the numerical simulations reported in the following publication:

> Jing Y, Chen Z, Wang H, et al. Energy dissipation mechanisms in topologically interlocking structures. Int J Mech Sci. 2025; 297-298:110317. https://doi.org/10.1016/j.ijmecsci.2025.110317

##Files

- TI-P-60kPa.inp：Example Abaqus input file demonstrating the equivalent confining pressure method
- README.md：Project description file

##Method Overview

This method was originally developed to replicate the chainmail structure studied by Wang et al. [1,2], in which interlocking hollow octahedral particles exhibit tunable stiffness under varying confining pressures. In Abaqus, we simulate the variable-pressure environment by enclosing the interlocking structure with a “constraining membrane”, to achieve an equivalent confining pressure effect.

Key components of the method include:
- An outer membrane constructed using Shell or Membrane elements 
- Elastic membrane material with“no failure or damage”
- A time-dependent pressure is applied to the outer surface of the membrane using the Amplitude keyword  
- Use of“General Contact” to couple the membrane and the internal structure  

This setup simulates a “vacuum environment”, where the internal pressure is zero and an external negative pressure is applied, resulting in isotropic contraction of the membrane and confinement of the internal structure.

##Abaqus Settings

-Solver framework：Abaqus/Explicit
-Loading method：Pressure + Amplitude 
-Contact definition：General Contact

##Limitations

- This method does not simulate air flow or permeability; the confinement is purely mechanical  
- If the membrane mesh is too fine, wrinkling or simulation failure may occur — choose appropriate mesh size and loading rate to ensure stability

##References

[1]Wang Y, Li L, Hofmann D, et al. Structured fabrics with tunable mechanical properties. Nature. 2021;596(7871):238-243.doi: 10.1038/s41586-021-03698-7
[2]Tian Y, Chen K, Zheng H, et al. Additively Manufactured Dual‐Faced Structured Fabric for Shape‐Adaptive Protection. Adv Sci. 2023;10(21).doi: 10.1002/advs.202301567

##Authors

South China University of Technology  
School of Civil Engineering and Transportation  
Department of Engineering Mechanics  
Yunjie Jing (Ph.D. Candidate)  
Shuchang Long (Associate Professor)  
Guangzhou, Guangdong, China  
July 18, 2025

##License

This project is intended for academic research and educational purposes only. Commercial use is prohibited. If you use this method or any part of this repository, please cite the following publication appropriately.
