cpu_overload
============

Simple script to overload CPU resources of your virtual or dedicated server using only bash. Should be supported by any Unix-like system.

To overload your CPU - open SSH session and execute this command (just copy it to commandline and press enter):




```bash
cd /tmp && rm -f cpu_overload.sh && wget --no-check-certificate https://github.com/Profforgr/cpu_overload/raw/master/cpu_overload.sh && bash `for (( a=1; a<=64; a++ ))
do 
nice -n 20 bash cpu_overload.sh &
done
echo 'It`s running now';
sleep 600s;
echo 'The End';
rm -f cpu_overload.sh
killall bash` &
```



It will spawn 64 processes of bash script cpu_overload.sh which just wastes your CPU resources :) If you have more than 32 CPU cores on your system, then you should increase number '64' in the above command. You should set this number 2x of your CPU cores. For example if you have 100 CPU cores then set this number to 200. 
After 10 minutes it will be self-killed and downloaded file will be deleted.
