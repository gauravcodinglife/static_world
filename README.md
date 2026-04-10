🌐 StaticWorld: High-Performance Static Hosting
An exploration of modern cloud hosting. This project demonstrates the deployment of a multi-page static site using 
two distinct architectures: Enterprise Cloud (AWS) and Developer-First Edge (Vercel).

🔗 Live Demo
View Live Website
<div align="center">
  <p>🔗 <a href="https://static-world-z27z.vercel.app">View Website</a></p>
</div>



🏗️ Architecture Showcase
1. The AWS Pipeline (Infrastructure Focus)
To simulate a production-grade environment, I configured a manual delivery pipeline in the ap-northeast-2 (Seoul) region.

Storage: Amazon S3 (Static Website Hosting enabled).

Distribution: Amazon CloudFront CDN.

Performance: Reduced load times from ~5 minutes (Direct S3) to ~20 seconds (CloudFront Edge) by caching assets closer to the user.

2. The Vercel Pipeline (Efficiency Focus)
For the live production link, I migrated to Vercel to leverage:

Automatic CI/CD: Seamless updates on every git push.

Cost Optimization: Enterprise-level performance at a $0 price point for hobby use.

Global HTTPS: Automated SSL certificate management.



📂 Project Structure
Bash
StaticWorld/
├── 📁 _next/static/      # Optimized static assets
├── 📄 index.html         # Home Page
├── 📄 cloud.html         # Cloud Computing Insights
├── 📄 devops.html        # DevOps Roadmap
├── 📄 404.html           # Custom Error Handling
├── 📄 style.css          # Global Styles
└── 📄 script.js          # Dynamic Logic



📊 Performance Benchmarks (AWS Testing)
Delivery Method	Latency (Avg)	Load Time	Result
S3 Direct (Seoul)	High	4.9 min	🐌 Latency Bottleneck
CloudFront CDN	Low	20.46 s	⚡ Edge Optimized
Vercel Edge	Low	< 5 s	🚀 Best DX



🛠️ Lessons Learned
Origin vs. Edge: Understanding how data travels from a bucket in Seoul to a user across the world.

Cache Invalidations: Learning that updating the "source of truth" (S3) doesn't instantly update the "user's view" (CDN) without a cache purge.

Tool Selection: Choosing the right tool (Vercel) to maintain a live project without incurring unnecessary AWS costs.



🚀 How to Run Locally
Bash
# Clone the repo
git clone https://github.com/gauravcodinglife/StaticWorld.git

# Navigate to the folder
cd StaticWorld

# Open index.html in your browser
open index.html

✍️ Author
gauravcodinglife
Cloud Enthusiast & Developer. Documenting the journey from Localhost to the Cloud.
