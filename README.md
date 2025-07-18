# graylog

Custom Logrus hook for sending structured logs to a Graylog server via GELF over TCP.

## 🔧 Purpose

This library is built for internal use within the [HydrAIDE Core](https://github.com/hydraide/core) and [HydrAIDE Server](https://github.com/hydraide/server) projects.  
Its goal is to provide **centralized, structured logging** with runtime control over log levels — and resilience when Graylog is unavailable.

> ⚠️ This library is designed for production-grade systems where logs must be shipped reliably and with context — even if Graylog goes offline.

---

## ✨ Features

- Sends logs to Graylog using the GELF protocol over TCP
- Captures stack traces automatically for `warn` level and above
- Supports dynamic log level changes at runtime
- Gracefully falls back to local file storage if Graylog is unreachable
- Automatically retries sending local logs once Graylog becomes available
- Includes service name in each log for filtering/grouping

---

## 📦 Installation

```bash
go get github.com/hydraide/graylog
