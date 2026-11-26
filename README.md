export const config = { runtime: 'edge' };

export default async function handler(req) {
  const url = new URL(req.url);
  url.hostname = '://googleapis.com';
  url.port = '';
  url.protocol = 'https:';
  const headers = new Headers(req.headers);
  headers.set('Host', '://googleapis.com');
  return fetch(url.toString(), {
    method: req.method,
    headers,
    body: req.body,
  });
}
