# ウェブアプリケーション課題 課題3
[![CircleCI](https://circleci.com/gh/cs3238-tsuzu/coding_challenge_03.svg?style=svg)](https://circleci.com/gh/cs3238-tsuzu/coding_challenge_03)
[![Coverage Status](https://coveralls.io/repos/github/cs3238-tsuzu/coding_challenge_03/badge.svg?branch=add_circleci)](https://coveralls.io/github/cs3238-tsuzu/coding_challenge_03?branch=add_circleci)
[![Go Report Card](https://goreportcard.com/badge/github.com/cs3238-tsuzu/coding_challenge_03)](https://goreportcard.com/report/github.com/cs3238-tsuzu/coding_challenge_03)
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/tsuzu/coding_challenge_03.svg)](https://hub.docker.com/r/tsuzu/coding_challenge_03)
## Usage
- With Go 1.12 or higher
    - Prepare PostgreSQL database
    - `export POSTGRES_DSN="host=address port=5432 user=your_user password=your_password dbname=your_dbname sslmode=disable"`
    - `go run github.com/cs3238-tsuzu/coding_challenge_03 --migrate`

- With Docker and docker-compose
    - Download `docker-compose.yml` and `.env`
    - Run `docker-compose up -d`
    - Recommended: before starting, set secure password in `POSTGRES_PASSWORD` in `.env`

## How to run tests
- `docker-compose -f docker-compose.circleci.yml up -d`
- `docker-compose -f docker-compose.circleci.yml exec app bash -c "cd /go/src/coding_challenge_03 && dockerize -wait tcp://db:5432 && go test -v -cover -race -coverprofile=./coverage.out ./..."`

## License
- Under the MIT License
- Copyright (c) 2019 Tsuzu