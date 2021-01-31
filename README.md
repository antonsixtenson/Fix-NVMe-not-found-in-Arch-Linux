# Fix-NVMe-not-found-in-Arch-Linux
This fix is a temporary fix for the problem regarding the WD Black NVMe SSD (in Acer-Aspire 3 laptop computers)

# PROBLEM:

<b>The NVMe SSD (WD Black) in this case in Acer Aspire 3 A315-23 Laptop.</b>

# SOLUTION:
<b> Solution works for Kernel 5.10.7-3</b>

Edit startup parameters (by pressing ‘e’ at grub menu) to include nvme_core.default_ps_max_latency_us=5500 put this after quiet (or quiet splash)
After install and when restarting again edit startup parameters in the same way.
Finally, when fresh install is booted: edit /etc/default/grub in the same way one last time. Finish it of by running sudo update-grub to make the parameter run without having to edit the parameters at every startup.

# ADDITIONAL NOTES:

This fix seems applicable for Arch Linux (including Manjaro) and Ubuntu.

The solution is based on (max latency setting to 5500us) Samsung controllers where APST is at 1500us/6000us.
