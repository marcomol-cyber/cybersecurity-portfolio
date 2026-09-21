# Python Algorithm for Updating an Allow List

## Project description

In this project, I used Python to automate the process of updating an allow list of IP addresses.

The scenario involved a healthcare organization that uses IP addresses to control access to a restricted subnetwork containing sensitive patient information. The organization maintains an allow list of IP addresses that are authorized to access the restricted network and a remove list containing IP addresses that should no longer have access.

The goal was to create an algorithm that identifies IP addresses from the remove list, removes them from the allow list, and updates the original file with the revised list.

## Open the file that contains the allow list

I stored the name of the allow-list file in the `import_file` variable and opened the file using Python's `open()` function.

```python
import_file = "allow_list.txt"

with open(import_file, "r") as file:
```

The `"r"` mode opens the file for reading. The `with` statement manages the file operation and ensures that the file is properly closed after the operation is completed.

## Read the file contents

I used `file.read()` to read the contents of the allow-list file and stored the result in the `ip_addresses` variable.

```python
ip_addresses = file.read()

print(ip_addresses)
```

At this stage, the IP addresses were stored as a single string containing the contents of the file.

## Convert the string into a list

I converted the string into a list using the `.split()` method.

```python
ip_addresses = ip_addresses.split()

print(ip_addresses)
```

This separated the individual IP addresses into list elements, making it possible to perform operations on each address individually.

## Iterate through the allow list

I used a `for` loop to iterate through the elements of the `ip_addresses` list.

```python
for element in ip_addresses:
    print(element)
```

The loop processes each IP address individually, allowing the algorithm to check each address against the remove list.

## Identify and remove unauthorized IP addresses

For each IP address, I checked whether it was present in the `remove_list`.

```python
for element in ip_addresses:
    if element in remove_list:
        ip_addresses.remove(element)
```

If an IP address was found in the remove list, I used the `.remove()` method to delete it from the allow list.

This allows the algorithm to automatically remove IP addresses that should no longer have access to the restricted network.

## Update the allow-list file

After removing the required IP addresses, I used `.join()` to convert the remaining list elements back into a single string.

```python
ip_addresses = " ".join(ip_addresses)
```

I then opened the original file in write mode and used `file.write()` to update its contents.

```python
with open(import_file, "w") as file:
    file.write(ip_addresses)
```

The `"w"` mode allows the file to be written with the updated allow list.

## Summary

This project helped me practice using Python to automate a basic access-control task. I worked with file operations, strings, lists, `for` loops, conditional statements, and list methods to identify and remove IP addresses that should no longer be authorized.

From a cybersecurity perspective, this type of automation can help security teams maintain access-control lists more efficiently and reduce the risk of outdated or unauthorized IP addresses remaining in a restricted network's allow list.
