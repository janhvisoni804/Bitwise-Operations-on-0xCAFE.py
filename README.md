val = 0xCAFE
print("Starting value:", hex(val))
last4 = val & 0xF   
count = 0
if last4 & 1: count += 1
if last4 & 2: count += 1
if last4 & 4: count += 1
if last4 & 8: count += 1
if count >= 3:
    print("1. At least 3 of the last 4 bits are ON")
else:
    print("1. Less than 3 of the last 4 bits are ON")
low = val & 0xFF           
high = (val >> 8) & 0xFF   
reversed_val = (low << 8) + high
print("2. After reversing bytes:", hex(reversed_val))
rotated_val = ((val << 4) + (val >> 12)) & 0xFFFF
print("3. After rotating 4 bits:", hex(rotated_val))
