FROM node:14-alpine

WORKDIR /app

# --- PATH CONFIGURATION ---
# We add '/app/node_modules/.bin' to the $PATH environment variable.
# This allows us to run executables (like react-scripts, nodemon, or tsc) 
# directly by name without needing to type the full path or install them globally.
ENV PATH /app/node_modules/.bin:$PATH

# Install application dependencies
COPY package*.json ./
RUN npm install

# Note: We no longer need 'npm install react-scripts -g' because the 
# ENV PATH line above lets Docker find the local version in node_modules.
# RUN npm install react-scripts -g

# Copy app files
COPY . .

EXPOSE 3000
CMD ["npm", "start"]
