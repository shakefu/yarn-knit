FROM shakefu/yarn-knit:base

ONBUILD COPY \
    package.json \
    yarn.lock \
    /usr/src/app/

ONBUILD ENTRYPOINT ["yarn", "run"]
ONBUILD CMD ["start"]

