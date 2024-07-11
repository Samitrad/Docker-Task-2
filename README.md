- Healthcheck is a mechanism to check the health of a container. It's like a doctor checking a patient's vital signs to ensure they're healthy.
ex:
 healthcheck:
       test: ["CMD-SHELL", "curl --fail http://localhost:5000/ || exit 1"]
       interval: 30s
       timeout: 10s
       retries: 3
- Run a command (curl --fail http://localhost:5000/ || exit 1) every 30 seconds (interval) to check if the web service is healthy.
- If the command fails, the container is considered unhealthy.
- If the command fails 3 times in a row (retries), the container is considered unhealthy.
- The healthcheck has a timeout of 10 seconds (timeout), meaning that if the command takes longer than 10 seconds to complete, it's considered a failure. 
- When a container is unhealthy, Docker can take actions such as restarting the container or sending a notification.
