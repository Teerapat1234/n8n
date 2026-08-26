# n8n - But with most nodes replaced with as much local dependencies as possible

## Quick Start

Try n8n instantly with [npx](https://docs.n8n.io/hosting/installation/npm/) (requires [Node.js](https://nodejs.org/en/)):

```
npx n8n
```

Or deploy with [Docker](https://docs.n8n.io/hosting/installation/docker/):

```
docker volume create n8n_data
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```

Access the editor at http://localhost:5678

## Moving Volume - run this command on the folder you want to keep it (command for Windows) 

docker run --rm -v n8n_data:/source -v ${PWD}:/backup alpine tar -cvf /backup/volume_backup.tar -C /source .

Then move the .tar into a folder inside your raspberrypi
Run this to create, apply new volume

*Run this inside wherever you placed your .tar
docker volume create n8n_data
docker run --rm -v n8n_data:/dest -v $(pwd):/backup alpine sh -c "tar -xvf /backup/volume_backup.tar -C /dest"

----------------------------------once you set it up-------------------------------------------

-running
The webhooks are a massive headache since we're hosting it on a website + local port forwarding.
So if you wanna call the MCP node you need to call it from local... run not n8ndrsomi.org run

## Resources

- 📚 [Documentation](https://docs.n8n.io)
- 🔧 [400+ Integrations](https://n8n.io/integrations)
- 💡 [Example Workflows](https://n8n.io/workflows)
- 🤖 [AI & LangChain Guide](https://docs.n8n.io/advanced-ai/)
- 👥 [Community Forum](https://community.n8n.io)
- 📖 [Community Tutorials](https://community.n8n.io/c/tutorials/28)

## License

n8n is [fair-code](https://faircode.io) distributed under the [Sustainable Use License](https://github.com/n8n-io/n8n/blob/master/LICENSE.md) and [n8n Enterprise License](https://github.com/n8n-io/n8n/blob/master/LICENSE_EE.md).

- **Source Available**: Always visible source code
- **Self-Hostable**: Deploy anywhere
- **Extensible**: Add your own nodes and functionality
