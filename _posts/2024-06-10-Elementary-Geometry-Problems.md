---
layout: post
_title: EGMOTC 2023 Elementary Geometry 
tags : ["Olympiad Geometry"]
---

Firstly, welcome to European Girls' Mathematical Olympiad Training camp 2023!I am so happy for all of you and very excited to teach all of you. 

Elementary Geometry doesn't have any prerequisite. So do not be scared. And now, let's try to do some maths!

I will be using Kenneth Peng's Geometry Through Problems as the main reference for the classes. 

<div class='example'>
  Let $ABCD$ be a quadrilateral. Let $M,N,P,Q$ be the midpoints of sides $AB,BC,CD,DA$. Prove that $MNPQ$ is a parallelogram.
</div>
<div class='proof'>
  Consider $\Delta ABD$ and  $\Delta BDC$ .Note that $NP||BD||MQ$. Similarly, $NM||AC||PQ$. Hence the parallelogram.
</div>

<div class='example'>
 In $\Delta ABC$, $\angle A$ be right. Let $D$ be the foot of the altitude from $A$ onto $BC$. Prove that $AD^2=BD\cdot CD$.
</div>
<div class='proof'>
  Note that $\Delta ADB\sim \Delta CDA$. So by similarity, we have $$\frac{AD}{BD}=\frac{CD}{AD}.$$
</div>

<div class='example' text='Angle Bisector Theorem'>
 In $\Delta ABC$, $\angle A$ be right. Let $D$ be the foot of the altitude from $A$ onto $BC$. Prove that $AD^2=BD\cdot CD$.
</div>
<div class='proof'>
  Let $D\in CA$, such that $AD = AB$.Note that $BD||AS$. So by the Thales’ Proportionality Theorem, we are done!
</div>

<div class='example'>
Given $\Delta ABC$, construct equilateral triangles $\Delta BCD,\Delta CAE,\Delta ABF$ outside of $\Delta ABC$. Prove that $AD=BE=CF$.
</div>
<div class='proof'>
This is just congruence. Note that in $\Delta ABD, \Delta FBC$ we have $$\angle FBC=\angle ABC+60^{\circ}=\angle ABD.$$ And $FB=AB,BC=BD$. So we get $\Delta ABD \cong \Delta FBC$. So $AD=FC$. Similarly, we can show $BE=FC$.
</div>

<div class='example' text='Menelaus Theorem'>
If line $PQ$ intersecting $AB$ on $\triangle ABC$, where $P$ is on $BC$, $Q$ is on the extension of $AC$, and $R$ on the intersection of $PQ$ and $AB$, then\[\frac{PB}{CP} \cdot \frac{QC}{QA} \cdot \frac{AR}{RB} = 1.\]
</div>
<div class='proof'>
Draw a line parallel to $QP$ through $A$ to intersect $BC$ at $K$.
$$\triangle RBP \sim \triangle ABK \implies \frac{AR}{RB}=\frac{KP}{PB}$$
$$\triangle QCP \sim \triangle ACK \implies \frac{QC}{QA}=\frac{CP}{KP}$$
Multiplying the two equalities together to eliminate the $PK$ factor, we get:
$\frac{AR}{RB}\cdot\frac{QC}{QA}=\frac{CP}{PB}\implies \frac{AR}{RB}\cdot\frac{QC}{QA}\cdot\frac{PB}{CP}=1$
</div>

<div class='example' text='Miquels Theorem'>
In $\Delta ABC$, choose points $D,E,F$ on sides $BC,CA,AB$ respectively. Prove that circles $(AEF),(BFD),(CDE)$ share a point known as the miquel point. 
</div>
<div class='proof'>
Define $M=(AEF)\cap (BFD)$. So note that $$\measuredangle FME=\measuredangle A,\measuredangle EMD=\measuredangle C\implies \measuredangle FMD=B\implies M\in (DFB).$$
</div>

<div class='example' text='Reims Theorem'>
Let $\omega_1, \omega_2$ be two circles intersecting at $M,N$. Let line $\ell_M$ through $M$ intersect $\omega_1, \omega_2$ at $A_1, A_2$. Let $B_1, B_2$ be points on $\omega_1, \omega_2$ respectively, Then $A_1B_1\parallel A_2B_2$ if , and only if, $B_1,N,B_2$ are collinear on a line $\ell_N$.
</div>
<div class='proof'>
Suppose that B_1NB_2 is a straight line. Then $$\measuredangle MA_1B_1 = \measuredangle MNB_1 = \measuredangle MA_2B_2 \implies A_1B_1 \parallel A_2B_2.$$
</div>

<div class='example' text='Simson Line'>
Let a triangle $\triangle ABC$ and a point $P$ be given. Let $D, E,$ and $F$ be the foots of the perpendiculars dropped from P to lines AB, AC, and BC, respectively. Then points $D, E,$ and $F$ are collinear iff the point $P$ lies on circumcircle of $\triangle ABC.$
</div>
<div class='proof'>
Let the point $P$ be on the circumcircle of $\triangle ABC.$ So $$\angle BFP = \angle BDP = 90^\circ \implies BPDF \text{ is cyclic }\implies \angle PDF = 180^\circ – \angle CBP.$$
So $$\angle ADP = \angle AEP = 90^\circ \implies AEPD \text{ is cyclic }$\implies \angle PDE = \angle PAE.$$
And $$ACBP \text{ is cyclic } \implies \angle PBC = \angle PAE \implies \angle PDF + \angle PDE = 180^\circ$$
$\implies D, E,$ and $F$ are collinear as desired.
</div>

<div class='example' text=''>
Let $AB$ be a chord in $\omega(O, r)$ and let $TA$ be a tangent to $\omega$ at $A$. Let $\angle BAT = \alpha$. Let $\angle APB$ be any inscribed angle over the arc $AB$. Then $$\angle BAT=\angle APB.$$
</div>
<div class='proof'>
Since $TA$ is a tangent, then it must be perpendicular to $OA$. So  $\angle OAT = 90^{\circ}$. So $\angle OAB = \angle OAT − \angle BAT = 90− \alpha$. 
Note that $\Delta OAB$ is isosceles. So  $$\angle OAB = \angle OBA = 90^{\circ} − \alpha,\angle AOB = 180^{\circ} −2(90^{\circ} −\alpha) = 2\alpha.$$ And $\angle APB=\angle AOB/2=\alpha$. So done.
</div>

## Olympiad Problems 
<div class='example' text='STEMS 2024, CAT A, P3'>
Let $ABC$ be a triangle. Let $I$ be the Incenter of $ABC$ and $S$ be the midpoint of arc $BAC$. Define $IA$ as the $A$-excenter wrt $ABC$. Define $\omega$ to be the circle centred at $S$ with radius $SB$. Let $AI_A \cap \omega = X$, $Y$. Show that $\angle BCX = \angle ACY$.
</div>
<div class='proof'>
 Note that$$\angle AYC=\angle XYC=\angle XBC.$$And we have$$\angle BXC=180-\frac{BSC}{2} = 180 - \frac{A}{2}.$$And note that $X-A-Y$ is the angle bisector of $\angle BAC$. So$$\angle YAC=180-\frac{A}{2}.$$So we get that$$\Delta BXC\sim\Delta YAC\implies \angle BCX=\angle ACY.$$
</div>
<div class='example' text=''>
Let $ABC$ be a triangle. The incircle of $ABC$ has center $I$ and is tangent to $AB$
and $AC$ at $D$ and $E$ respectively. Let $O$ denote the circumcenter of $BCI$. Prove
that $\angle ODB = \angle OEC$.
</div>
<div class='proof'>
Note that $A,I,O$ are collinear. Now $$\triangle ADO \cong \triangle AEO \implies \angle ODB = \angle OEC$$ 
</div>

<div class='example' text='USAJMO 2020/4'>
Let $ABCD$ be a convex quadrilateral inscribed in a circle and satisfying $DA < AB = BC < CD$. Points $E$ and $F$ are chosen on sides $CD$ and $AB$ such that $BE \perp AC$ and $EF \parallel BC$. Prove that $FB = FD$.
</div>
<div class='proof'>
Let $P = AC \cap BE$. Since $\triangle{ABC}$ is isosceles we know that $P$ is the mid point of $AC$. Let $\angle{CBE} = \angle{ABE} = \alpha$. We also know that $\angle{BCA} = \angle{BAC} = 90 - \alpha$. By parallel lines we know that $\angle{FEB} = \alpha$. Hence $\triangle{FEB}$ is isosceles or $FB = FE$.

Let $\angle{DCA} = \angle{DBA} = \theta$. By parallel lines we see that $\angle{DEF} = 90 - \alpha + \theta$. Since $EP \perp AC$ and $P$ is the midpoint of $AC$ as previously stated, we know that $\triangle{AEC}$ is isosceles or $\angle{EAC} = \angle{ECA} = \theta$.

Note that $AFED$ is cyclic due to\[\angle{AFE} + \angle{ADE} = 180 - \angle{BFE} + 180 - \angle{ABC} = 180 - (180 - 2\alpha) + 180 - 2\alpha = 180.\]Hence we know that $\angle{FAE} = \angle{FAC} + \angle{CAE} = 90 - \alpha + \theta = \angle{FDE}$ meaning that $\angle{FDE} = \angle{FED}$ or $\triangle{FED}$ is isosceles.

Therefore we know that $FE = FD$. Previously we found that $FB = FE$, thus we get $FB = FE$ as desired.
</div>

<div class='example' text='IMO 2000/1'>
Two circles $G_1$ and $G_2$ intersect at two points $M$ and $N$. Let $AB$ be the line tangent to these circles at $A$ and $B$,
respectively, so that $M$ lies closer to $AB$ than $N$. Let $CD$ be the line parallel to $AB$
and passing through the point $M$, with $C$ on $G_1$ and $D$ on $G_2$. Lines $AC$ and $BD$ meet at $E$; lines $AN$ and $CD$ meet at $P$;
lines $BN$ and $CD$ meet at $Q$. Show that $EP = EQ$.
</div>
<div class='proof'>
Let $MN\cap AB=P \implies M$ is midpoint of $PQ.$  It is enough to show that $EM\cap CD$ or show that $EM\cap AB.$ Note that $$\angle ACM=\angle,~~\angle EAB=\angle ECD.$$ So $EAMB$ is kite. And we are done.
</div>

<div class='example' text='2019/G1'>
Let $ABC$ be a triangle. Circle $\Gamma$ passes through $A$, meets segments $AB$ and $AC$ again at points $D$ and $E$ respectively, and intersects segment $BC$ at $F$ and $G$ such that $F$ lies between $B$ and $G$. The tangent to circle $BDF$ at $F$ and the tangent to circle $CEG$ at $G$ meet at point $T$. Suppose that points $A$ and $T$ are distinct. Prove that line $AT$ is parallel to $BC$.

</div>
<div class='proof'>
Redefine $T$ such that $T\in (ABC)$ and $AT||BC$.
<div class='claim'>
  $TF$ tangent to $(BDF)$.
</div>
  <div class='proof'>
    Note that is enough to show that $180-\angle BDF=\angle BFT$. But note that$$\angle BDF=\angle TFG=\angle FTA.$$
  </div>
Similarly, we get that $TG$ is tangent to $(EGC)$. And we are done.
</div>

<div class='example' text='EGMO 2016/P4'>
Two circles $\omega_1$ and $\omega_2$, of equal radius intersect at different points $X_1$ and $X_2$.
Consider a circle $\omega$ externally tangent to $\omega_1$ at $T_1$ and internally tangent to $\omega_2$ at point $T_2$.
Prove that lines $X_1T_1$ and $X_2T_2$ intersect at a point lying on $\omega$.
</div>
<div class='proof'>
Note that the composition of homotheties gives us$$ \omega_1 \xrightarrow{T_1} \omega \xrightarrow{T_2} \omega_2. $$Moreover, since the product of scales are $-1$ ( not $1$, else it will be a transformation), so the composition is a homothety.

But the homothety taking $\omega_1\rightarrow \omega_2$ is simply $1$ or $-1$ ratio as the radius is the same and the centre lies on $O_1O_2$. But ratio $1$ is absurd. Hence,the ratio is $-1$ with the centre of the homothety being the midpoint of $X_1X_2,O_1O_2$.

Let $M$ be the midpoint of $O_1O_2,X_1X_2$. So note that$$\omega_1\xrightarrow{O} \omega_2=\omega_1 \xrightarrow{T_1} \omega \xrightarrow{T_2} \omega_2.$$But the homothety $\omega_1\xrightarrow{O} \omega_2$ takes $X_1\rightarrow X_2$. Now, we consider the homothety $\omega_1 \xrightarrow{T_1} \omega \xrightarrow{T_2} \omega_2$, this takes$$X_1\rightarrow X_1T_1\cap \omega \text { say } A \rightarrow AT_2\cap \omega_2.$$But we should have $AT_2\cap \omega_2=X_2$. So $T_2-A-X_2$. And we are done!
</div>

<div class='example' text='EGMO 2012 P1'>
Let $ABC$ be a triangle with circumcentre $O$. The points $D,E,F$ lie in the interiors of the sides $BC,CA,AB$ respectively, such that $DE$ is perpendicular to $CO$ and $DF$ is perpendicular to $BO$. (By interior we mean, for example, that the point $D$ lies on the line $BC$ and $D$ is between $B$ and $C$ on that line.)
Let $K$ be the circumcentre of triangle $AFE$. Prove that the lines $DK$ and $BC$ are perpendicular.
</div>
<div class='proof'>
Note that $\angle FKE=2\angle A$ and$$\angle OBC=\angle OCB=90-\angle A\implies \angle FDB=\angle EDC=A\implies \angle FDE=180-2\angle A\implies KFDE \text{ cyclic}.$$
As$$KF=KE\implies \angle KEF=90-A\implies \angle KDF=90-A\implies $$$$\angle KDB=\angle KDF+\angle FDB=90$$$$\implies KD\perp BC.$$And we are done.
</div>

<div class='example' text='IMO 2023 P2'>
Let $ABC$ be an acute-angled triangle with $AB\le AC$. Let $\Omega$ be the circumcircle of $ABC$. Let $S$ be the midpoint of the arc $CB$ of $\Omega$ containing $A$. The perpendicular from $A$ to $BC$ meets $BS$ at $D$ and meets $\Omega$ again at $E \neq A$. The line through $D$ parallel to $BC$ meets line $BE$ at $L$. Denote the circumcircle of triangle $BDL$ by $\omega$. Let $\omega$ meet $\Omega$ again at $P \neq B$. Prove that the line tangent to $\omega$ at $P$ meets line $BS$ on the internal angle bisector of $\angle BAC$.


</div>
<div class='proof'>
Define $A'$ as the antipode of $A$. And redefine $P=A'D\cap (ABC)$. Define $L=SP\cap (PDB)$. 
<div class='claim'>
   $L-B-E$ collinear
</div>
<div class='proof'>
  Note that $$\angle SCA=\angle SCB-\angle ACB=90-A/2-C.$$
So $$\angle SPA=90-A/2-C\implies \angle SPA'=90-(90-A/2-C)=A/2+C\implies \angle LBD=A/2+C\implies \angle LBD=A/2+C.$$
By angle chase, $$\angle DBC=90-A/2,\angle EBC=90-C.$$ So $E-B-L$ collinear.
</div>

<div class='claim'>
  $LD||BC$
</div>
<div class='proof'>
  Define $F$ as midpoint of arc $BC$ not containing $A$.
Now define $X=PP\cap AF$. Define $O$ as the circumcenter of $(ABC)$. 
We know that $$\angle EBC=90-C,\angle ELD=\angle BLD=\angle BPD=\angle BPA'=\angle BAO=90-C.$$
So $LD||BC$.

</div>
<div class='claim'>
  $PXOF$ is cyclic
</div>
<div class='proof'>
   Let $\angle PAB=\theta$. So $\angle PSB=\theta$ and $\angle PSF=\theta+A/2$. So $\angle POF=2\theta+A$. 
And $\angle PXF=\angle PAX+\angle APX$. But $\angle PAX=\theta+A/2$. And $$\angle APX=\angle APS+\angle SPX=\angle ACS+\angle SPX=90-A/2-C+\angle SPX.$$
So to show cyclicity, we need to show that $$2\theta+A=\angle PXF=90+\theta-C+\angle SPX.$$
Or enough to show $$\angle SPX=\theta+A-90+C.$$
But $$\angle SPX=\angle SPB-\angle XPB$$ 
$$=\angle SAB-\angle XPD-\angle DPB= 90+A/2-\angle DBP-\angle DLB$$
$$=90+A/2-\angle DLP-(90-C)$$
$$=C+A/2-\angle DLP$$
as $SF||AD,BC||LD, AD\perp BC$ we get $$C+A/2-\angle DLP=C+A/2-(90-A/2-\theta)=C+A-90+\theta.$$
And so we get $PXOF$ is cyclic.
</div>
<div class='claim'>
  $XA=XP$
</div>
<div class='proof'>
  Note that $$\angle XPA=\angle PXF-\angle PAX=2\theta+A-\theta-A/2=\theta+A/2$$. So $\angle XPA=\angle XAP$. And hence the claim.
But $$XA^2=XP^2=XD\cdot XB.$$ So $XA$ is tangent to $(DBA)$. Hence $$\angle ABD=\angle DAS=\angle DAF=\angle AFS=\angle ABS.$$

</div>
And hence we get $B-X-S$ collinear.

And we are done! 
</div>

<div class='example' text='2008 G1'>
Let $ H$ be the orthocenter of an acute-angled triangle $ ABC$. The circle $ \Gamma_{A}$ centered at the midpoint of $ BC$ and passing through $ H$ intersects the sideline $ BC$ at points $ A_{1}$ and $ A_{2}$. Similarly, define the points $ B_{1}$, $ B_{2}$, $ C_{1}$ and $ C_{2}$.

Prove that the six points $ A_{1}$, $ A_{2}$, $ B_{1}$, $ B_{2}$, $ C_{1}$ and $ C_{2}$ are concyclic.
</div>
<div class='proof'>
<div class='claim'>
  $A_1A_2C_1C-2$ is cyclic
</div>
<div class='proof'>
   Note that $H$ lies on the radical axis of $(C_1C_2)$ and $(A_1A_2)$. Moreover, we know that $BH$ is perpendicular to line joining the centre. So $BC_2\cdot BC_1=BA_1\cdot BA_2\implies A_1A_2C_1C_2$ cyclic.

</div>
Similarly, we get $A_1A_2B_1B_2$ and $B_1B_2C_1C_2$ cyclic. If these three circles are not the same then, consider the pairwise radical axis which should concur( but they don't).
</div>

<div class='example' text='USAMO 2021'>
Rectangles $BCC_1B_2,$ $CAA_1C_2,$ and $ABB_1A_2$ are erected outside an acute triangle $ABC.$ Suppose that\[\angle BC_1C+\angle CA_1A+\angle AB_1B=180^{\circ}.\]Prove that lines $B_1C_2,$ $C_1A_2,$ and $A_1B_2$ are concurrent.

</div>
<div class='proof'>
<div class='claim'> Circumcircles of $B_1A_2AB, AA_1C_2C,$ and $BCC_1B_2$ mutually intersect at some point $P.$
</div>
<div class='proof'>
Let $P$ be $(BCC_1B_2)\cap (CAA_2C_2)$. Note that
$$\angle AB_1B=180^\circ-(\angle BC_1C+\angle CA_1A)$$ 
$$=\angle BPC+\angle APC-180^\circ=180^\circ - \angle APB$$
</div>
<div class='claim'> Lines $B_1C_2, C_1A_2,$ and $A_1B_2$ concur at $P.$
</div>
<div class='proof'>
But $$\angle A_2PB=\angle BPC_1=90^\circ.$$
</div>
So done!
</div>

<div class='example' text='2015 P1'>
Let $\triangle ABC$ be an acute-angled triangle, and let $D$ be the foot of the altitude from $C.$ The angle bisector of $\angle ABC$ intersects $CD$ at $E$ and meets the circumcircle $\omega$ of triangle $\triangle ADE$ again at $F.$
If $\angle ADF = 45^{\circ}$, show that $CF$ is tangent to $\omega .$
</div>
<div class='proof'>
Note that $\angle FDE=45$. As $F$ lies on the angle bisector and $FD$ is the external bisector of $\angle CDB$, we get that $F$ is the $B-$ excenter of $\Delta CDB$.
Note that$$FCD=\frac{180-(\angle DCB)}{2}=\frac{180-90+\angle B}{2}=45+\frac{\angle B}{2}$$and$$\angle AED=180-\angle FEA-\angle DEB=180-45-90+\frac{\angle B}{2}=45+ \frac{\angle B}{2}$$$$\implies CF||AF$$
So$$\angle FEA=\angle FAE=\angle AFX, X\in \overrightarrow{ CF}.$$
</div>

<div class='example' text='IISC Pravega'>
Let $ABC$ be a triangle inscribed in circle $\omega$ centered at $O$. Let $H$ be the orthocenter of $\triangle ABC$. Let $Q$ be a point on $\omega$ such that $\angle AQH = 90^\circ$. Let $N$ be the nine point center of $\triangle QBC$. Show that $HO= 2 HN$.
</div>
<div class='proof'>
Let the orthocentre of $QBC$ be $J$. Let $L$ be the $N_9$ center of $ABC$. Let $M$ be the midpoint of $BC.$ Note that $Q-H-M$
<div class='claim'> 
   $AQJH$ is a parallelogram $\implies QM\perp NL$
</div>
<div class='proof'>
 Note that $NL||HJ$. Note that$$ AH\perp BC,QJ\perp BC\implies AH||QJ, AH=2R\cos (A)=QJ\implies AQJH\text{ is a parallelogram }.$$
</div>
<div class='claim'> 
  $MN=ML$
</div>
<div class='proof'>
As the radius of nine point circle is $1/2$ radius of the circumcircle, but $(QBC)=(ABC).$
</div>

So $Q-H-M$ is the perpendicular bisector of $NL$. Hence$$ HN=HL\implies HO=2HN.$$
</div>
<div class='claim'> 

</div>
<div class='proof'>

</div>
<div class='example' text='2015 G1'>
Let $ABC$ be an acute triangle with orthocenter $H$. Let $G$ be the point such that the quadrilateral $ABGH$ is a parallelogram. Let $I$ be the point on the line $GH$ such that $AC$ bisects $HI$. Suppose that the line $AC$ intersects the circumcircle of the triangle $GCI$ at $C$ and $J$. Prove that $IJ = AH$.
</div>
<div class='proof'>
<div class='claim'> 
$GBHC$ cyclic
</div>
<div class='proof'>
Note that $HC\perp HG$ as $HC\perp AB$. And $GB\perp BC$ as $AH\perp BC$. So $GBHC$ cyclic.
</div>

Note that$$\angle HBG=\angle HBC+\angle CBG=90-C+90=180-C\implies \angle HCG=C\implies 90-C=\angle IGC=\angle IJC.$$But$$\angle IA'A=\angle A'AH=90-C\implies IJ=IA'=AH.$$
</div>

<div class='example' text='2020 G1'>
Let $ABC$ be an isosceles triangle with $BC=CA$, and let $D$ be a point inside side $AB$ such that $AD\le DB$. Let $P$ and $Q$ be two points inside sides $BC$ and $CA$, respectively, such that $\angle DPB = \angle DQA = 90^{\circ}$. Let the perpendicular bisector of $PQ$ meet line segment $CQ$ at $E$, and let the circumcircles of triangles $ABC$ and $CPQ$ meet again at point $F$, different from $C$.
Suppose that $P$, $E$, $F$ are collinear. Prove that $\angle ACB = 90^{\circ}$
</div>
<div class='proof'>
Let $N$ be the midpoint of $AB$, $M$ be the midpoint of $PQ$.
Note that$$\angle CND=90\implies N\in (CPDQF).$$
Also, $CN$ is the angle bisector $\angle BCA \implies CN$ is the angle bisector of $\angle PCQ\implies NP=NQ\implies C-M-E$.
But$$\angle PNC=\angle CQP=\angle FPQ=\angle FNQ.$$So $\triangle PNC \cong \triangle FNQ \implies M\in $ perpendicular bisector of $CF$.

So $M$ is the circumcentre of $(ACB)$ as perpendicular bisector of $AB$ and $CF$ concur at $M$.
</div>

<div class='example' text='India TST 2015 P1'>
Diagonals ${AC}$ and ${BD}$ of convex quadrilateral $ABCD$ meet at $P$. Prove that the incenters of the triangles
$\triangle PAB$, $\triangle PBC$, $\triangle PCD$, $\triangle PDA$ are concyclic if and only if their $P$-excenters are also concyclic.
</div>
<div class='proof'>
Note that $AI_A\cdot AJ_A=AB\cdot AC.$
We then use POP $PA\cdot PB=PI_1\cdot PJ_1$ and we do it cyclically. Doing manipulations, we get that 
    $$\frac{(PI_2\cdot PE_2)(PI_4\cdot PE_4)}{(PI_1\cdot PE_1)(PI_3\cdot PE_3)}=1 $$ And then we take POP on $P$ in concyclicity etc.
</div>

<div class='example' text='2018 P1'>
Let $\Gamma$ be the circumcircle of acute triangle $ABC$. Points $D$ and $E$ are on segments $AB$ and $AC$ respectively such that $AD = AE$. The perpendicular bisectors of $BD$ and $CE$ intersect minor arcs $AB$ and $AC$ of $\Gamma$ at points $F$ and $G$ respectively. Prove that lines $DE$ and $FG$ are either parallel or they are the same line.
</div>
<div class='proof'>
Define $Q=GE\cap (ABC),P=DF\cap (ABC)$
<div class='claim'> 
$Q\in (ADE)$
</div>
<div class='proof'>
Note that$$\angle AQE=\angle AQG=\angle GCA=\angle GCE=\angle GEC=\angle AEQ.$$
</div>
Hence, if $D$ is the midpoint of major arc $BC$, note that $A-I-D$ and $D$ is the centre of $(BIC).$ Note that by triangle inequality we have$$AD\le AP+PD\implies AI+ID\le AP+PD\implies AI\le AP.$$
</div>

<div class='example' text='IMO 2013 P4'>

</div>
<div class='proof'>
Define $Z=(BWX)\cap (CWY)$
<div class='claim'> 
$X-Z-Y$ collinear
</div>
<div class='proof'>
As $XW$ is the diameter, we have $\angle XZW=90$, similarly, we have $\angle WZY=90$
</div>
<div class='claim'> 
$Z\in (ANHM)$
</div>
<div class='proof'>
Note that $Z$ is the miquel point. So $Z\in (ANM)$, But $H\in (ANM)\implies (ANHMZ)$ is cyclic.

</div>
Note that $NMCB$ is cyclic
<div class='claim'> 
$Z\in AW$
</div>
<div class='proof'>
Note that$$\angle NZW=180-\angle NBW=\angle NMC=180-\angle NMA=180-\angle NZA.$$
</div>
Now, note that$$\angle XZW=\angle HZA=90\implies H\in X-Z-Y.$$
</div>






