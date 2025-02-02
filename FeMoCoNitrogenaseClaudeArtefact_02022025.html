<!DOCTYPE html>
<html>
<head>
    <title>Nitrogenase Enzyme</title>
    <style>
        body { margin: 0; }
        canvas { display: block; }
        #info {
            position: absolute;
            top: 10px;
            left: 10px;
            color: white;
            font-family: Arial, sans-serif;
            background: rgba(0,0,0,0.7);
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div id="info">Nitrogenase Enzyme Structure<br>Iron-Molybdenum Cofactor (FeMo-co)<br>Click and drag to rotate</div>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js"></script>
    <script>
        // Initialize scene
        const scene = new THREE.Scene();
        scene.background = new THREE.Color(0x000000);

        // Set up camera
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        camera.position.z = 5;

        // Create renderer
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);

        // Add lights
        const ambientLight = new THREE.AmbientLight(0x404040);
        scene.add(ambientLight);

        const light1 = new THREE.PointLight(0xffffff, 1, 100);
        light1.position.set(10, 10, 10);
        scene.add(light1);

        const light2 = new THREE.PointLight(0xffffff, 0.8, 100);
        light2.position.set(-10, -10, -10);
        scene.add(light2);

        // Create nitrogenase complex
        const nitrogenase = new THREE.Group();

        // Create Fe-Mo cofactor (FeMo-co)
        const feMoCo = new THREE.Group();

        // Create iron atoms (Fe7)
        const ironGeometry = new THREE.SphereGeometry(0.2, 32, 32);
        const ironMaterial = new THREE.MeshStandardMaterial({ 
            color: 0xcc6600,
            metalness: 0.8,
            roughness: 0.2
        });

        // Position iron atoms in cubane-like structure
        const ironPositions = [
            [0, 0, 0],
            [0.4, 0.4, 0],
            [0, 0.4, 0.4],
            [0.4, 0, 0.4],
            [-0.4, -0.4, 0],
            [0, -0.4, -0.4],
            [-0.4, 0, -0.4]
        ];

        ironPositions.forEach(pos => {
            const iron = new THREE.Mesh(ironGeometry, ironMaterial);
            iron.position.set(...pos);
            feMoCo.add(iron);
        });

        // Add molybdenum atom
        const moGeometry = new THREE.SphereGeometry(0.25, 32, 32);
        const moMaterial = new THREE.MeshStandardMaterial({
            color: 0x4444ff,
            metalness: 0.9,
            roughness: 0.1
        });
        const mo = new THREE.Mesh(moGeometry, moMaterial);
        mo.position.set(0.6, 0.6, 0.6);
        feMoCo.add(mo);

        // Add sulfur atoms
        const sulfurGeometry = new THREE.SphereGeometry(0.15, 32, 32);
        const sulfurMaterial = new THREE.MeshStandardMaterial({
            color: 0xffff00,
            metalness: 0.3,
            roughness: 0.7
        });

        // Position sulfur atoms between iron atoms
        const sulfurPositions = [
            [0.2, 0.2, 0],
            [0.2, 0, 0.2],
            [0, 0.2, 0.2],
            [-0.2, -0.2, 0],
            [-0.2, 0, -0.2],
            [0, -0.2, -0.2],
            [0.4, 0.4, 0.4]
        ];

        sulfurPositions.forEach(pos => {
            const sulfur = new THREE.Mesh(sulfurGeometry, sulfurMaterial);
            sulfur.position.set(...pos);
            feMoCo.add(sulfur);
        });

        // Create bonds between atoms
        const bondMaterial = new THREE.MeshStandardMaterial({
            color: 0x888888,
            metalness: 0.5,
            roughness: 0.5
        });

        function createBond(start, end) {
            const direction = new THREE.Vector3().subVectors(end, start);
            const length = direction.length();
            
            const bondGeometry = new THREE.CylinderGeometry(0.03, 0.03, length, 8);
            const bond = new THREE.Mesh(bondGeometry, bondMaterial);
            
            // Position and rotate bond
            bond.position.copy(start);
            bond.position.lerp(end, 0.5);
            bond.quaternion.setFromUnitVectors(
                new THREE.Vector3(0, 1, 0),
                direction.normalize()
            );
            
            return bond;
        }

        // Add bonds between nearby atoms
        for (let i = 0; i < ironPositions.length; i++) {
            for (let j = i + 1; j < ironPositions.length; j++) {
                const start = new THREE.Vector3(...ironPositions[i]);
                const end = new THREE.Vector3(...ironPositions[j]);
                if (start.distanceTo(end) < 1) {
                    feMoCo.add(createBond(start, end));
                }
            }
        }

        // Add bonds to sulfur atoms
        sulfurPositions.forEach((sulfurPos, i) => {
            const sulfurVec = new THREE.Vector3(...sulfurPos);
            ironPositions.forEach(ironPos => {
                const ironVec = new THREE.Vector3(...ironPos);
                if (sulfurVec.distanceTo(ironVec) < 0.8) {
                    feMoCo.add(createBond(sulfurVec, ironVec));
                }
            });
        });

        // Add protein environment (simplified)
        const proteinGeometry = new THREE.TorusKnotGeometry(2, 0.1, 128, 16);
        const proteinMaterial = new THREE.MeshStandardMaterial({
            color: 0x88aaff,
            transparent: true,
            opacity: 0.3,
            roughness: 0.7
        });
        const protein = new THREE.Mesh(proteinGeometry, proteinMaterial);
        nitrogenase.add(protein);

        // Add active site highlight
        const activeSiteGeometry = new THREE.SphereGeometry(0.4, 32, 32);
        const activeSiteMaterial = new THREE.MeshStandardMaterial({
            color: 0xff0000,
            transparent: true,
            opacity: 0.3,
            emissive: 0xff0000,
            emissiveIntensity: 0.5
        });
        const activeSite = new THREE.Mesh(activeSiteGeometry, activeSiteMaterial);
        activeSite.position.copy(mo.position);
        feMoCo.add(activeSite);

        nitrogenase.add(feMoCo);
        scene.add(nitrogenase);

        // Orbit controls
        let isDragging = false;
        let previousMousePosition = { x: 0, y: 0 };
        
        renderer.domElement.addEventListener('mousedown', (e) => {
            isDragging = true;
            previousMousePosition = {
                x: e.clientX,
                y: e.clientY
            };
        });

        renderer.domElement.addEventListener('mousemove', (e) => {
            if (!isDragging) return;

            const deltaMove = {
                x: e.clientX - previousMousePosition.x,
                y: e.clientY - previousMousePosition.y
            };

            nitrogenase.rotation.y += deltaMove.x * 0.01;
            nitrogenase.rotation.x += deltaMove.y * 0.01;

            previousMousePosition = {
                x: e.clientX,
                y: e.clientY
            };
        });

        renderer.domElement.addEventListener('mouseup', () => {
            isDragging = false;
        });

        // Animation loop
        function animate() {
            requestAnimationFrame(animate);

            // Gentle rotation when not being dragged
            if (!isDragging) {
                nitrogenase.rotation.y += 0.001;
            }

            // Pulse active site
            const pulse = Math.sin(Date.now() * 0.003) * 0.3 + 0.5;
            activeSite.material.opacity = 0.2 + pulse * 0.2;
            activeSite.material.emissiveIntensity = pulse;

            renderer.render(scene, camera);
        }

        // Handle window resize
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });

        animate();
    </script>
</body>
</html>