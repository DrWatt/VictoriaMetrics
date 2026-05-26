## Setup Configuration

All configurations are included in the services in the ```service``` folder. They expect four folders:
```
/srv/victoria/one_week
/srv/victoria/one_month
/srv/victoria/six_months
/srv/victoria/all_data
```

In order to create a unified stack to manage the entire VictoriaMetrics database, all single retention policies and continuous queries services must be added to the stack with:

```
systemctl add-wants victoriametrics-stack.target vm-one_week.service
systemctl add-wants victoriametrics-stack.target vm-one_month.service
systemctl add-wants victoriametrics-stack.target vm-six_months.service
systemctl add-wants victoriametrics-stack.target vm-all_data.service
systemctl add-wants victoriametrics-stack.target vmagent-sensu.service
```

The CQs configurations have to be copied in ```/etc/vmagent/```.
