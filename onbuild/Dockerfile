FROM shakefu/yarn-knit:base

# Allow for build arg importing of NPM auth
ONBUILD ARG NPMRC=
ONBUILD RUN echo "$NPMRC" >> /root/.npmrc

# Copy in our package.json and yarn lockfile
ONBUILD COPY package.json yarn.lock /usr/src/app/

# Install things
ONBUILD RUN yarn install --pure-lockfile --prefer-offline --no-progress

# Copy in the rest of the code
ONBUILD COPY . .

# Set up our entrypoint and default command
ONBUILD ENTRYPOINT ["yarn", "run"]
ONBUILD CMD ["start"]

