# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-19 at 11 26 13](https://github.com/user-attachments/assets/29e3f22a-0761-4d11-8e9a-732ba53cb110)
![WhatsApp Image 2025-11-19 at 11 26 18](https://github.com/user-attachments/assets/8d0d108a-23ed-43e9-afd8-a9eeef6aa59f)
![WhatsApp Image 2025-11-19 at 11 26 17](https://github.com/user-attachments/assets/8d0c3659-ab9d-45d0-8c11-203159fd64fb)




## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:

<img width="1917" height="1033" alt="image" src="https://github.com/user-attachments/assets/c40f4be1-5c11-4f5b-9f25-c49315b3a15e" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.<br>
Gain margin = 0.7<br>
Phase Margin = -8.8865<br>
Gain crossover frequency = 3.7565<br>
Phase crossover frequency = 3.1623<br>
The system is unstable.<br>
