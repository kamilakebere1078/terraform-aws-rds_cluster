# Build RDS Instance
### Please copy paste below code
```
module "db" {
    source = "../"
    region = "us-east-2"
    subnet_ids = [
        "subnet-0fa96dbe96f0839c1",
        "subnet-0ad819957cc0a2825",
        "subnet-0f863d4023eeef6cc"
    ]
    identifier          = "dbname"
    allocated_storage   = 20
    storage_type        = "gp2"
    engine              = "aurora-mysql"
    engine_version      = "5.7.mysql_aurora.2.07.2"
    instance_class      = "db.t2.micro"
    username            = "foo"
    publicly_accessible = true
    db_access = [
        "50.194.68.230/32",
        "50.194.68.231/32",
        "0.0.0.0/0"
    ]
}
```
### NOTE: Password will be created in SSM