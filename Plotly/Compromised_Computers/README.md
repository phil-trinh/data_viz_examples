# Compromised Computers
This puzzle comes from Dr. Chiara Sabatti at Stanford University as a summary of some real network traffic data from the past. The dataset has ~21K rows and covers 10 local workstation IPs over a three month period. Half of these local IPs were compromised at some point during this period and became members of various botnets. Can we discover when a compromise has occurred by a change in the pattern of communication?

Each row consists of four columns:  
date: yyyy-mm-dd (from 2006-07-01 through 2006-09-30)  
l_ipn: local IP (coded as an integer from 0-9)  
r_asn: remote ASN (an integer which identifies the remote ISP)  
f: flows (count of connnections for that day)

Reports of "odd" activity or suspicions about a machine's behavior triggered investigations on the following days (although the machine might have been compromised earlier)

**Date : IP**  
08-24 : 1  
09-04 : 5  
09-18 : 4  
09-26 : 3, 6  

In finding abnormal internet traffic, I figured box plots would be the best choice as any major outliers are distinguishable. For each compromised computer IP, [1, 3, 4, 5, 6], I aggregated the mean number of connections per day together since means are susceptive to outliers. The box plot has the hover info to be the date of that value, so the max values will more likely to be the time that the compromised computer. The max values are either on or before the date of investigation specified above.

I chose to highlight the suspected outliers (in bold outlines) for each box plot to show these were other times that the computer could be compromised as well, since they are out of the inner distribution of the dataset.