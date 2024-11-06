You may have an error message for the Datanode that the `vm.max_map_count` value is too low. This setting controls the maximum number of memory map areas a process may have. For Graylog to function properly, this value needs to be at least `262144`.

To fix this issue, you need to increase the `vm.max_map_count` value on your host system. You can do this by running the following command on your Linux host:
```sh
sudo sysctl -w vm.max_map_count=262144
```

To make this change permanent, you can add the following line to your `sysctl.conf` file:
```sh
vm.max_map_count=262144
```

After adding the line, you can apply the changes without restarting the machine by running:
```sh
sudo sysctl -p
```
This will ensure that the `vm.max_map_count` value is set correctly both immediately and after a system reboot.