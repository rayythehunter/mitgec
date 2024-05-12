
1. Installing WSL
```powershell
% wsl --install
```

2. Install X11 Apps (xeyes, dll)
```bash
% sudo apt install x11-apps -y
```

3. Gfortran
```bash
% sudo apt install gfortran
% gfortran --version
```

4. Clone MITgcm
```bash
% git --version
% git clone https://github.com/MITgcm/MITgcm.git
```

5. Python PIP
```bash
% sudo apt install python3
% python --version
% sudo apt install python3-pip
% pip install MITgcmutils
% pip install xmitgcm
```

6. Build Model
```bash
% cd MITgcm/
% cd verification/exp2/build/
% ../../../tools/genmake2 -mods ../code -optfile ../../../tools/build_options/linux_amd64_gfortran
% make depend
% make
```

7. Run Model
```bash
% cd ../run
% ln -s ../input/* .
% cp ../build/mitgcmuv .
% ./mitgcmuv
% ./mitgcmuv > output.txt
```

8. * Run Model (MPI)
```bash
% sudo apt install lam-runtime
% lamboot
% mpirun -np 4 ./mitgcmuv
```


https://mitgcm.readthedocs.io/en/latest/getting_started/getting_started.html#