FROM shakefu/yarn-knit:base

ONBUILD COPY package.json yarn.lock /usr/src/app/

ONBUILD RUN yarn install --pure-lockfile --prefer-offline --no-progress
ONBUILD COPY . .

ONBUILD ENTRYPOINT ["yarn", "run"]
ONBUILD CMD ["start"]

