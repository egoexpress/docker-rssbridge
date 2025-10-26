# RSS-Bridge Docker Repository Guidelines

## Build/Test Commands
- `docker-compose up -d` - Start RSS-Bridge service
- `docker-compose down` - Stop RSS-Bridge service  
- `docker-compose logs app` - View application logs
- `docker-compose exec app sh` - Access container shell
- `docker network create proxy_frontend` - Create required external network
- `docker-compose pull && docker-compose up -d` - Update and restart service

## Code Style Guidelines
- Use YAML 2-space indentation for docker-compose.yml
- Environment variables in UPPERCASE_SNAKE_CASE
- Keep Docker image tags specific (YYYY-MM-DD format)
- Use descriptive service names (e.g., "app" not "web")
- Volume names in snake_case, network names use underscores for external networks
- Maintain alphabetical ordering: services, networks, volumes
- Include restart policy for production containers
- Use external networks for reverse proxy integration
- Environment variables referenced with ${VAR_NAME} syntax
- Keep service definitions minimal and focused

## Commit guidelines
- Push code to GitHub after commit
- Use Conventional Commit style commit messages
