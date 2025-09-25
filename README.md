# Infotact_Solutions_Internship_2025_August_Project_1
Snort rule creation &amp; testing project — detects SSH brute-force (5 attempts in 60s) inside a reproducible VirtualBox lab.

## Repository layout
Infotact_Solutions_Internship_2025_August_Project_1/  
├─ README.md  
├─ LICENSE (MIT)  
├─ demo/  
│ └─ future_demo_link.txt  
│ └─ network_diagram.png  
├─ lab-setup/  
│ └─ VM_setup_guide.md  
├─ password-list/  
│ └─ password_list.txt  
├─ report/  
│ └─ infotact_solutions_report_project_1_nids_snort_analetizia_simono.pdf  
├─ snort/  
│ └─ local.rules  
└─   snort.conf.txt  

## Executive summary
This project implements and validates a custom Snort rule to detect SSH brute-force attempts in an isolated VM lab (Ubuntu Server victim, Kali attacker). The rule alerts when a single source IP makes **5 SSH connection attempts within 60 seconds**. Hydra-driven testing triggered timely, actionable alerts, demonstrating a measurable reduction in mean-time-to-detect for this attack class. See `report/infotact_solutions_report_project_1_nids_snort_analetizia_simono.pdf` for full evidence and timestamps.

## Quick start (runbook)
> Assumes attacker (Kali) and victim (Ubuntu Server) VMs on the same network.

1. Clone repo:
```bash
git clone https://github.com/<you>/Infotact_Solutions_Internship_2025_August_Project_1.git
cd Infotact_Solutions_Internship_2025_August_Project_1
```

Follow the `lab-setup/VM_setup_guide.md` document.

## Evidence &amp; Artifacts
- infotact_solutions_report_project_1_nids_snort_analetizia_simono.pdf - full write-up with screenshots and timestamps
- demo/ - demo video link

## Troubleshooting Notes (quick)
- After editing rules, restart Snort to apply changes
- Use `tmux` to run Snort in one pane and commands/tests in another
- Take screenshots before starting Snort console to preserve scroll state

## Ethics &amp; Scope
All testing was performed on isolated VMs owned by the project owner. No public or unauthorized systems were targeted.

## License &amp; Contact
MIT License - see `LICENSE (MIT)`
Analetizia Simono - Security Associate L1 (Intern), Infotact Solutions - https://www.linkedin.com/in/analetizia-simono-18b551346/
