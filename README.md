Telemetry and tracing of AI agents. Currently mainly for use with agents running with [OpenCode](https://opencode.ai/).

### Usage

Start the [OpenTelemetry](https://opentelemetry.io/) collector for collecting traces and the [Jaeger](https://www.jaegertracing.io/) observability backend for inspecting the traces inside docker containers:

```sh
docker compose up
```

In order for traces to be sent to the collector, the config for OpenCode inside `opencode.json` has
to be placed in the root directory OpenCode is executed inside.

The plugin for getting the traces is [opencode-plugin-otel](https://github.com/DEVtheOPS/opencode-plugin-otel).

### Notes

Changing the configuration for plugins of OpenCode requires any running instance of the background server to be stopped, because the config has to be consistent.

```sh
# find the running process
ps aux | grep "[o]pencode"

# stop the process
pkill -f "opencode serve"
```
