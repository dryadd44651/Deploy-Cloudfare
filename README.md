# Deploy-Cloudfare
This repository serves as a resource for managing the configurations and deployment processes of my projects.

#list tunnel
cloudflared tunnel list

# create tunnel
cloudflared tunnel create <NAME>

# For workout back/front end
cloudflared tunnel create wrokout

# rename(not work)
cloudflared tunnel rename oldTunnelName newTunnelName

# delete
cloudflared tunnel delete wrokoutUI

# Very important! Follow this instruction to add the CNAME with UUID (9cf25586-1994-4498-bee4-7129cfacd1d5)
https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/routing-to-tunnel/dns/
# add CNAME with UUID (you can do this with this command or do it in the cloudfare dashboard)
cloudflared tunnel route dns 9cf25586-1994-4498-bee4-7129cfacd1d5 workout


# copy the credentials-file to here
cp "C:\Users\dryad\.cloudflared\9cf25586-1994-4498-bee4-7129cfacd1d5.json" ./.cloudflared/


cloudflared tunnel --config ./.cloudflared/workout_config.yml run workout


# run workout backend
cloudflared tunnel run workout
cloudflared tunnel --config ./.cloudflared/workout_config.yml run workout



# check info
cloudflared tunnel info <UUID or NAME>
