# Voxchain
Système de vote citoyen numérique - France
cat > package.json << 'EOF'
{
  "name": "voxchain",
  "version": "1.0.0",
  "description": "Système de vote citoyen numérique - France",
  "private": true,
  "scripts": {
    "dev": "vercel dev",
    "deploy": "vercel --prod"
  },
  "dependencies": {
    "@supabase/supabase-js": "^2.39.0",
    "twilio": "^4.19.0",
    "@sendgrid/mail": "^8.1.0",
    "bcryptjs": "^2.4.3",
    "jsonwebtoken": "^9.0.2"
  },
  "engines": {
    "node": ">=18.0.0"
  }
}
EOF
