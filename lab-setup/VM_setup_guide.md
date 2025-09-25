# VM Setup Guide
1. Victim (Ubuntu) — install &amp; verify:
```
sudo apt update && sudo apt upgrade && sudo apt install -y snort openssh-server
sudo systemctl status ssh
ip a            # note interface (e.g., enp0s3)
```

2. Install rule:
```
# copy repository's local.rules to Snort rules directory
sudo cp snort/local.rules /etc/snort/rules/local.rules
# ensure /etc/snort/snort.conf includes: include $RULE_PATH/local.rules
```

3. Start Snort (replace interface):
```
sudo snort -A console -q -c /etc/snort/snort.conf -i enp0s3
```

4. Attacker (Kali) — run Hydra (replace <VM_IP>):
```
hydra -l non_existent_user -P scripts/pass.txt ssh://<VM_IP>
```

5. Observe alerts in Snort console or /var/log/snort/alert.

## Rule (snort/local.rules)
```
alert tcp any any -> $HOME_NET 22 (msg:"SSH Brute-Force Attempt Detected"; flow:to_server,established; detection_filter:track by_src, count 5, seconds 60; sid:1000002; rev:1;)
```