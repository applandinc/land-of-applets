# How to properly close a Net::SSH connection?

Demonstration program for Stack Overflow question https://stackoverflow.com/questions/62643718/how-to-properly-close-a-netssh-connection.

# Usage

```
# Build and run an SSH server
docker-compose build
docker-compose up -d
# Run the test program
bundle exec ruby main.rb
# Upload the AppMap
appland upload tmp/appmap.json
docker-compose down -v
```

# `Net::SSH` code operation details

## Public key authentication (disallowed)

[![Public key auth (disallowed)](public-key-auth.png)](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=1795&filterShow=stack_depth_less%2Csql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests&filterShowParams=%7B%22stack_depth_less%22%3A%228%22%7D)

## Password authentication (allowed)

[![Password auth (disallowed)](password-auth.png)](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=2295&filterShow=stack_depth_less%2Csql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests&filterShowParams=%7B%22stack_depth_less%22%3A%228%22%7D)

## Closing the session

[![Closing the session](closing-session.png)](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=7254&filterShow=stack_depth_less%2Csql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests&filterShowParams=%7B%22stack_depth_less%22%3A%228%22%7D)

