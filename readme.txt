def uniqueUpdate(data1, data2):
    # Initially empty dictionary
    dupKeys = {}

    # Examine every (k, v2) pair in data2
    for k, v2 in data2.items():
        # Search for a key-value pair
        # with key = k in data1
        # (no such pair found yet)
        kFound = False

        for [k1, v1] in data1:
            if k1 == k:
                # Found pair with key = k
                kFound = True

                if v1 != v2:
                	# Remove (k, v1) from data1
                	data1.remove([k,v1])
                	# Add (k, [v1, v2])
                	# to dictionary
                	dupKeys[k] = [v1,v2]
  
        # After the loop, check if
        # k was not found
        if not kFound:
            # Add (k, v2) to data1
            data1.append([k, v2])

    # After processing all (k, v2) in
    # data2, return the dictionary
    return dupKeys
