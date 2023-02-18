FROM diamol/node

ENV MAX_ALLOCATION_MB=4096 \
    LOOP_ALLOCATION_MB=512 \
    LOOP_INTERVAL_MS=2000

# my solution to lab
CMD node memory-check.js && node memory-hog.js

HEALTHCHECK --interval=5s --timeout=2s --start-period=3s --retries=2 CMD [ "node", "memory-check.js" ]

# CMD ["node", "memory-hog.js"]

WORKDIR /app
COPY src/ .